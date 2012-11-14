### Restoring a heroku backup to a local database
	pg_restore -v -h localhost -c -O -d clubmin_development -U clubmin a075.dump

-v = verbose
-c = execute any drop statements in the backup (drop and re-create tables for this restore)
-O = do not enforce ownership (leave db ownership as it is)
-d = specify database name to restore to (in this example clubmin_development)
a075.dump = the backup filename from heroku
