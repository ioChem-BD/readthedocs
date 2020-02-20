Define backup policy
====================

| We must backup the databases and software folder to be able to restore our system in case of data loss or corruption and as a safeguard before updating the platform.
| We can code an script and crontab it to backup those elements into a backup destination folder.

The following is a sample script that dumps the databases and compresses the platform folder into a single backup file.

.. code:: bash

   #!/bin/bash
   BACKUP_FOLDER=/home/iochembd/backup     # <-- Set your backup folder here
   IOCHEM_FOLDER=/home/iochembd/iochembd   # <-- Set your ioChem-BD installation folder here

   #sufix will range values 0..5 for each week number of the month, change the expression to suit your backup needs 
   sufix=$[`date +%e`/7]
   BACKUP_FOLDER=$BACKUP_FOLDER/$sufix
   rm -fr $BACKUP_FOLDER
   mkdir -p $BACKUP_FOLDER

   # Dump PostgreSQL databases, we must provide user password to allow dump to work properly, so please restrict script file rights to 700
   export PGUSER=iochembd
   export PGPASSWORD=                      # <-- Set iochembd database user password
   pg_dump --inserts -h 127.0.0.1 -f $BACKUP_FOLDER/dump_iochemCreate.sql "iochemCreate"
   pg_dump --inserts -h 127.0.0.1 -f $BACKUP_FOLDER/dump_iochemBrowse.sql "iochemBrowse"
   unset PGUSER
   unset PGPASSWORD

   #Zip databases
   gzip -f $BACKUP_FOLDER/dump_iochemCreate.sql
   gzip -f $BACKUP_FOLDER/dump_iochemBrowse.sql

   #Zip entire ioChem-BD folder
   tar -zcvf $BACKUP_FOLDER/iochembd.tar.gz $IOCHEM_FOLDER
