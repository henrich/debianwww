
.. toctree::
   index
   nonvuln

====================================================================================
Key Rollover
====================================================================================

In :doc:`Debian Security Advisory 1571 </support/security/2008/dsa-1571>`,
the Debian Security Team disclosed a weakness in the random number generator used
by OpenSSL on Debian and its derivatives. As a result of this weakness,
certain encryption keys are much more common than they should be, such that an
attacker could guess the key through a brute-force attack given minimal knowledge
of the system.  This particularly affects the use of encryption keys in OpenSSH,
OpenVPN and SSL certificates.

This page documents how to perform key rollover procedures for packages
whose keys are affected by the OpenSSL vulnerability.

Other software uses cryptographic keys, but is :doc:`not vulnerable <notvuln>`
as OpenSSL is not used to generate or exchange its keys.

 * ckermit
 * GnuPG
 * Iceweasel
 * MySQL


For key rollover instructions for other software, you might want to check
the user-submitted information in https://wiki.debian.org/SSLkeys


OpenSSH
========================================================================================

An updated package has been released via
:doc:`DSA-1576 </support/security/2008/dsa-1576>`, which eases key transformation.

 #. Install the security updates in DSA-1576 

    Once the update is applied, weak user keys will be automatically
    rejected where possible (though they cannot be detected in all
    cases).  If you are using such keys for user authentication, they
    will immediately stop working and will need to be replaced (see
    step 3). 

    OpenSSH host keys can be automatically regenerated when the OpenSSH
    security update is applied.  The update will prompt for confirmation
    before taking this step.

 #. Update OpenSSH known_hosts files

    The regeneration of host keys will cause a warning to be displayed when
    connecting to the system using SSH until the host key is updated in the
    :file:`known_hosts` file on the client.  The warning will look like this::

       @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
       @    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
       @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
      IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
      Someone could be eavesdropping on you right now (man-in-the-middle attack)!
      It is also possible that the RSA host key has just been changed.

    In this case, the host key has simply been changed, and you should update
    the relevant :file:`known_hosts` file as indicated in the warning message.
   
    It is recommended that you use a trustworthy channel to exchange the
    server key.  It is found in the file :file:`/etc/ssh/ssh_host_rsa_key.pub` on
    the server; it's fingerprint can be printed using the command::

        ssh-keygen -l -f /etc/ssh/ssh_host_rsa_key.pub

    In addition to user-specific known_hosts files, there may be a
    system-wide file :file:`/etc/ssh/ssh_known_hosts`.  This file is
    used both by the ssh client and by sshd for the hosts.equiv
    functionality.  This file needs to be updated as well.

 #. Check all OpenSSH user keys 

    The safest course of action is to regenerate all OpenSSH user keys,
    except where it can be established to a sufficient high degree of certainty
    that the key was generated on an unaffected system.

    Check whether your key is affected by running the ssh-vulnkey tool, included
    in the security update.  By default, ssh-vulnkey will check the standard
    location for user keys (:file:`~/.ssh/id_rsa`, :file:`~/.ssh/id_dsa` and :file:`~/.ssh/identity`),
    your authorized_keys file (:file:`~/.ssh/authorized_keys` and
    :file:`~/.ssh/authorized_keys2`), and the system's host keys
    (:file:`/etc/ssh/ssh_host_dsa_key` and :file:`/etc/ssh/ssh_host_rsa_key`).

    * To check all your own keys, assuming they are in the standard
      locations (:file:`~/.ssh/id_rsa`, :file:`~/.ssh/id_dsa`, or :file:`~/.ssh/identityP`)::

        ssh-vulnkey

    * To check all keys on your system::
      
        sudo ssh-vulnkey -a

    * To check a key in a non-standard location::
 
        ssh-vulnkey /path/to/key

    If ssh-vulnkey says "`Unknown (no blacklist information)`", then it has no
    information about whether that key is affected.  If in doubt, destroy the
    key and generate a new one.

 #. Regenerate any affected user keys

    OpenSSH keys used for user authentication must be manually regenerated,
    including those which may have been transferred to a different system
    after being generated. 

    New keys can be generated using ssh-keygen, e.g.::

      $ ssh-keygen
      Generating public/private rsa key pair.
      Enter file in which to save the key (/home/user/.ssh/id_rsa):
      Enter passphrase (empty for no passphrase):
      Enter same passphrase again:
      Your identification has been saved in /home/user/.ssh/id_rsa.
      Your public key has been saved in /home/user/.ssh/id_rsa.pub.
      The key fingerprint is:
      00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00 user@host
 

 #. Update authorized_keys files (if necessary)

    Once the user keys have been regenerated, the relevant public keys
    must be propagated to any authorized_keys files (and authorized_keys2
    files, if applicable) on remote systems.  Be sure to delete the
    affected key. 


OpenSSL: Generic PEM key generation instructions
========================================================================================

This is just a reminder for those who (re-)generate PEM encoded
certificates. Your site probably has other policies in place about how
to manage keys which you should follow. Additionally, you may need to
get the certificates signed again by a 3rd party Certificate Authority
rather than by using a self-signed certificate as shown below::

  cd /etc/ssl/private
  openssl genrsa 1024 > mysite.pem
  cd /etc/ssl/certs
  openssl req -new -key ../private/mysite.pem -x509 -days 9999 -out mysite.pem


Other vulnerable software
========================================================================================
  
bincimap
----------------------------------------------------------------------------------------
The bincimap package automatically creates a self-signed certificate
through the openssl program for the bincimap-ssl service, and puts it
into /etc/ssl/certs/imapd.pem. To regenerate, run::

  rm -f /etc/ssl/certs/imapd.pem
  dpkg-reconfigure bincimap


boxbackup
----------------------------------------------------------------------------------------

Boxbackup is not present in Debian stable, only in testing/Lenny.
Upstream has published a first impact analysis of key material created
on system with insufficient random PRNG. You can read the details
`here <http://lists.warhead.org.uk/pipermail/boxbackup/2008-May/004476.html>`_.

If the PRNG in your OpenSSL was insufficiently random, you need to:

 * Regenerate all affected certificates, which have been generated or
   signed on an affected system
 * Regenerate all the data keys (\*-FileEncKeys.raw)
 * Destroy the data stored on your server to an appropriate level of
   security (overwrite with zeros at the least, more if you're paranoid)
 * Upload everything again
 * Take appropriate measures under the assumption that you have been
   storing your data in plain text on a public server without authentication.
   (i.e., start from scratch, destroying all trace of the backed up
   data, and take other measures to mitigate the exposure of your
   secrets)

cryptsetup
----------------------------------------------------------------------------------------
Cryptsetup itself does not use openssl for encryption (this applies to
both LUKS and dm-crypt devices).

*If* cryptsetup has been configured to use SSL-encrypted keyfiles (a
non-default setup which must be explicitly configured by the user)
and a broken version of openssl was used to generate the keyfile, the
keyfile encryption may be weaker than expected (as the salt is not
truly random).

The solution is either to re-encrypt the keyfile (if you are
reasonably certain that the encrypted key has not been disclosed to
any third parties) or to wipe and reinstall the affected partition(s) 
using a new key.

Instructions for re-encrypting a keyfile:

* Do the following for each SSL-encrypted keyfile, replacing
  <ssl_encrypted_key_path> with the path to the actual keyfile::

     tmpkey=\$(tempfile)
     openssl enc -aes-256-cbc -d -salt -in <ssl_encrypted_key_path> -out "$tmpkey"
     shred -uz <ssl_encrypted_key_path>
     openssl enc -aes-256-cbc -e -salt -in "$tmpkey" -out <ssl_encrypted_key_path>
     shred -uz "$tmpkey"

dropbear
----------------------------------------------------------------------------------------
If you have :file:`/etc/ssh/*host*` keys, either remove them, or follow the
:ref:`openssh instructions <openssh>` first, before updating dropbear's
keys.

Dropbear's postinst converts existing openssh keys to dropbear format,
if it cannot find the dropbear host keys.::

  rm /etc/dropbear/*_host_key
  dpkg-reconfigure dropbear

Note that keys that have been generated by Dropbear itself are not
vulnerable (it uses libtomcrypt rather than OpenSSL).


ekg
----------------------------------------------------------------------------------------
Users of programs ekg or ekg2 (the latter is only in experimental) who
use the "SIM" encryption functionality, who generated a keypair using
the ``/key [-g|--generate]`` command (which uses libssl to do the job)
should regenerate the keys, after upgrading libssl and restarting the
program.

 * The upstream developers have posted a notice on their website:
   http://ekg.chmurka.net/index.php

 * If you need further help, please ask on ekg-users@lists.ziew.org or
   ekg2-users@lists.ziew.org (both English and Polish).

ftpd-ssl
----------------------------------------------------------------------------------------
Below command covers the default setup::

  rm -f /etc/ftpd-ssl/ftpd.pem /etc/ssl/certs/ftpd.pem
  dpkg-reconfigure ftpd-ssl

If the local admin has setup further SSL infrastructure beyond that,
these keys will need to be regenerated as well.


gforge
----------------------------------------------------------------------------------------
The gforge-web-apache2 package in sid and lenny sets up the website
with a dummy certificate if no existing certificate is found. Users are then
encouraged to replace it with a "real" one. The dummy certificate in
question is the Snake Oil one, so it should already be known as a weak
one (even without the SSL bug), but some users may accept
it without a second thought. 

MIT Kerberos (krb5)
----------------------------------------------------------------------------------------
 * No part of MIT Kerberos in Debian 4.0 ("Etch") uses OpenSSL, and so Kerberos
   in Debian 4.0 is not affected at all.

 * In Lenny the separate binary package krb5-pkinit uses OpenSSL.  MIT
   Kerberos itself does not generate long-term key pairs even when the PKINIT
   plugin is used, so any vulnerable long-term key pairs would have been
   generated outside of the MIT Kerberos software itself. The PKINIT plugin
   only references existing key pairs and isn't responsible for key
   management.

 * Long-term key pairs used with PKINIT may be affected if generated on an
   affected Debian system, but such generation is external to MIT Kerberos.
 
 * However, the OpenSSL random key functions are used for the DH exchange
   when PKINIT authentication is used, which means that an attacker may be
   able to use brute-force to gain access to the KDC response to a PKINIT
   authentication and subsequently gain access to any sessions created using
   service tickets from that authentication.

 * Any KDCs using the PKINIT plugin from Lenny should have their libssl0.9.8
   packages upgraded immediately and the Kerberos KDC restarted with::

     /etc/init.d/krb5-kdc restart

 * Any Kerberos ticket-granting tickets (TGTs) or encrypted sessions resulting
   from PKINIT authentication using a Kerberos KDC with the affected libssl
   should be treated as suspect; it's possible that attackers with packet
   captures will be able to compromise those keys and sessions.

Nessus
----------------------------------------------------------------------------------------
The Nessus server package (nessusd) post installation script creates
some SSL keys for secure communication between a Nessus server and client.
That communication channel should be considered compromised since a rogue user
could be able to intercept the information exchanged between the server and the
client (which includes information of remote hosts vulnerabilities) and
potentially could send commands to the servers as the logged in user.

Additionally, if the admin has created either the Nessus CA key or a user
certificate (with nessus-mkcert-client) for remote authentication in a server
which had installed the OpenSSL version affected by this security issue those
keys should be considered compromised. Note that remote users with access to
the Nessus server can launch attacks to the servers they are allowed to attack
and, if enabled on the local configuration (in Debian it defaults to "`no`")
upload plugins which would be executed in the Nessus server with root
privileges.

The maintainer configuration scripts will regenerate the OpenSSL certificates
when configured if it cannot find them. You will need to remove the certificates
and have it generate new ones doing::

  rm -f /var/lib/nessus/CA/cacert.pem
  rm -f /var/lib/nessus/CA/servercert.pem
  rm -f /var/lib/nessus/private/CA/cakey.pem
  rm -f /var/lib/nessus/private/CA/serverkey.pem
  dpkg-reconfigure nessusd


Once this is done you will have to remove the old user keys
at /var/lib/nessus/users/USERNAME/auth and regenerate them again with
nessus-mkcert-client. Old keys will be invalid once the CA key has been removed.

fter the CA key is regenerated you will also need to distribute the new CA
certificate to your users, and your users will have to accept the new certificate
from the Nessus server once they reconnect. Certificate settings for the old
server should be removed automatically but you can also remove them manually by
editing the <code>.nessusrc.cert</code> (if using the Nessus client) or
<code>.openvasrc.cert</code> (if using the OpenVAS client).

OpenSWAN / StrongSWAN
----------------------------------------------------------------------------------------
Exec below::

  rm /etc/ipsec.d/private/`hostname`Key.pem /etc/ipsec.d/certs/`hostname`Cert.pem
  dpkg-reconfigure (open|strong)swan
  /etc/init.d/ipsec restart

Beware: Restarting the ipsec services terminates all currently open IPSec
connections, which may need to be restarted from the other end.

OpenVPN
----------------------------------------------------------------------------------------
Backup your secret key files. While key names are arbitrary, they can
be detected by running::

  grep secret /etc/openvpn/*.conf

Recreate them using::

  openvpn --genkey --secret SECRET_FILENAME

Then copy the shared secret keys to the remote hosts and restart the VPN
on each host with::

  /etc/init.d/openvpn force-reload


Proftpd
----------------------------------------------------------------------------------------
The Debian packaging doesn't include key generation, so the following
steps should only be necessary if SSL keys have been created externally.

An upcoming proftpd upload to unstable will include a tls.conf template
with the comment below.

Note that the self-signed certificate generation is bit
ifferent from that suggested on the general openssl section, in order
to avoid using of an explicit password at daemon startup.
 
You can (re-)generate a self-signed certificate using a command like::

     openssl req -x509 -newkey rsa:1024 \
      -keyout /etc/ssl/private/proftpd.key -out /etc/ssl/certs/proftpd.crt \
      -nodes -days 365

Both files must be readable by root only. The file paths can be
checked/configured through the following configuration directives::

  TLSRSACertificateFile                   /etc/ssl/certs/proftpd.crt
  TLSRSACertificateKeyFile                /etc/ssl/private/proftpd.key
  TLSCACertificateFile                    /etc/ssl/certs/CA.pem
  TLSOptions                              NoCertRequest


puppet
----------------------------------------------------------------------------------------
There are two methods to handle puppet certificates, one is via capistrano,
the second is manually.

 * Regenerating Puppet SSL Certificates using capistrano is detailed
   `here <http://reductivelabs.com/trac/puppet/wiki/RegenerateSSL>`_
 
 * The manual steps are as follows:

   #. You need to wipe and regenerate your CA info::

        /etc/init.d/puppetmaster stop
        rm -rf $vardir/ssl/*
        /etc/init.d/puppetmaster start

   #. However, if you are running mongrel, instead of starting puppetmaster from
      the init script, you will need to first stop the front-end web listener
      (apache, nginx, etc.) and then do the following::

        puppetmasterd --daemonize ; sleep 30 ; pkill -f 'ruby /usr/sbin/puppetmasterd'

   #. The above is necessary because for some reason when running with mongrel,
      puppetmaster will not regenerate its CA.

   #. Wipe all the client certs::

       /etc/init.d/puppet stop
       rm $vardir/ssl/*

   #. Have each client request a new cert::

       puppetd --onetime --debug --ignorecache --no-daemonize

   #. Once all the requests have rolled in, you can sign them all at once::

       puppetca --sign --all

   #. Start up your puppet clients::

       /etc/init.d/puppet start

      You could also enable autosign temporarily, if you are comfortable with that.

sendmail
----------------------------------------------------------------------------------------
Sendmail (both in Etch and in Lenny) optionally creates default OpenSSL
certificates at install time.

The key rollover procedure is trivial::

    /usr/share/sendmail/update_tls new

If you have customized the templates in :file:`/etc/mail/tls`, those
values will be re-used to create the new certificates.

ssl-cert
----------------------------------------------------------------------------------------
The snakeoil certificate /etc/ssl/certs/ssl-cert-snakeoil.pem can be
recreated with::

  make-ssl-cert generate-default-snakeoil --force-overwrite


telnetd-ssl
----------------------------------------------------------------------------------------
Run below::

  rm -f /etc/telnetd-ssl/telnetd.pem /etc/ssl/certs/telnetd.pem
  dpkg-reconfigure telnetd-ssl

This covers the default setup. If the local admin has setup further
SSL infrastructure beyond that, these keys will need to be regenerated
as well.


tinc
----------------------------------------------------------------------------------------
Remove all suspect public and private key files:

   #. Remove rsa_key.priv.
   #. Edit all files in the hosts/ directory and remove the public key blocks.

Generate a new public/private key pair::

     tincd -n <netname> -K

Exchange your host config file with the new public key with other
members of your VPN. Do not forget to restart your tinc daemons.


tor
----------------------------------------------------------------------------------------
 * Tor is not in stable, but affected in Lenny.

 * Clients running 0.1.2.x are not affected.  Tor nodes or hidden service
   providers running any version, as well as everyone on 0.2.0.x are
   affected.

 * Please see the `vulnerability announcement <http://archives.seul.org/or/announce/May-2008/msg00000.html>`_
   on the Tor announce mailing list.

 * Upgrading to 0.1.2.19-3 (available in testing, unstable, backports.org, and
   the usual `noreply.org repository <https://wiki.torproject.org/noreply/TheOnionRouter/TorOnDebian>`_)
   or 0.2.0.26-rc-1 (available in experimental and the usual
   `noreply.org repository <https://wiki.torproject.org/noreply/TheOnionRouter/TorOnDebian>`_)
   is recommended. If you run a relay these versions will force
   new server keys (:file:`/var/lib/tor/keys/secret_\*`) to be generated.

 * Should you run a Tor node without using the package's infrastructure
   (debian-tor user, :file:`/var/lib/tor` as DataDirectory etc.) you manually need
   to remove bad keys.  See the advisory link posted above.

 * If you are a hidden service provider, and have created your key in
   the affected timeframe with a bad libssl then please delete your hidden
   service's private key. This will change your hidden service's host name
   and may require reconfiguring your servers.

 * If you are running 0.2.0.x, an upgrade is highly recommended - 3 of the
   6 v3 authority servers have compromised keys.  Old 0.2.0.x versions
   will stop working in a week or two.


xrdp
----------------------------------------------------------------------------------------
xrdp uses generated keys. Most clients do not check those keys by
default, therefore changing them is painless. You just have to::

  rm /etc/xrdp/rsakeys.ini
  /etc/init.d/xrdp restart

xrdp is not in stable.	
