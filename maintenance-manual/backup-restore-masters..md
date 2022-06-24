# Backup/ Restore - Masters.

## TO MAKE DATABASE DUMP IN MONGODB

mongodump --host mongo.prv --db \<Database Name> --out \<Mention location to store backup data>

## TO RESTORE DATABASE DUMP IN MONGODB

mongorestore --host mongo.prv --db \<database name> \<Location of the stored backup data>

## TO MAKE COLLECTION DUMP IN MONGODB

mongodump --host mongo.prv --db \<Database Name> --collection \<Collection/Table Name for backup> --out \<Location to store backup>

## TO RESTORE SPECIFIC DATABASE COLLECTION IN MONGODB

mongorestore --host mongo.prv --collection \<Collection name to restore>--db \<Database name>
