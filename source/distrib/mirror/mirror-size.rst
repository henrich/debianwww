=============================================================
Mirror size
=============================================================

How big is the Debian archive?
=================================================

.. (note for the English editors on how to update some of the numbers below)
.. dak psql database on ftp-master is 'projectb'
.. and there's a copy on merkel
.. projectb=> select architecture.arch_string as Architecture,
..            sum(files.size)/1024/1024/1024 as Size
..            from files,binaries,architecture
..            where architecture.id=binaries.architecture
..            and files.id=binaries.file
..            group by architecture.arch_string
..            order by Size;
.. projectb=> select sum(size)/1024/1024/1024 from files where
..            filename ~ '.diff.gz$' or filename ~ '.dsc$'
..            or filename ~ '.orig.tar.gz$';
.. projectb=> select sum(files.size)/1024/1024/1024
..            from files, binaries, architecture
..           where architecture.id=binaries.architecture
..           and files.id=binaries.file
..           and architecture.arch_string='i386';

.. wc -c'ing files inside the debian/ directory might occasionally give
.. slightly different results than the SQL queries, but the difference
.. is usually negligible -joy


:include: size.data

Note that the archive is constantly growing; testing will grow especially
as a release approaches. Also, we do not recommend reducing size of a mirror
by excluding specific distributions; exclude specific architectures instead,
according to their <a href="http://popcon.debian.org/">popularity</a>.</p>

How big is the Debian Security archive?
=================================================

The debian-security archive is around 54 GB. ???fixed size??

How big is the old Debian archive?
=================================================


How big is the Debian CD archive?
=================================================

The CD archive varies greatly across mirrors &mdash; the Jigdo files are
around 100-150 MB per architecture, while the full DVD/CD images are
around 15 GB each, plus extra space for the <q>update</q> CD images,
Bittorrent files, etc.

For more information about the CD archive mirroring, please see
the <a href="../CD/mirroring/">Debian CD mirror pages</a>.

How big are the regular updates to the mirrors?
=================================================

For the main Debian archive, please see
<a href="https://ftp-master.debian.org/size-quarter.png">the graph of the
daily run size</a>.

