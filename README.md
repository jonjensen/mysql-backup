# mysql-backup

This is a Bourne shell program that uses `mysqldump` to export a MySQL server's data for backup. It has been in continuous use on many servers since the earliest simpler versions dating to around the year 1999.

Each database is exported into its own file in plain text format for archival and cross-version accesibility.

The database file is then compressed using one of the common compression tools, currently pxz, xz, lbzip2, pbzip2, bzip2, pigz, or gzip.

Each new export file is deleted if it is identical to the previous one so that the timestamp and inode will not change, to minimize changes visible to backup tools such as rsync.

Configuration allows optionally excluding some databases.
