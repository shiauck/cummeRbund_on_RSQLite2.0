# cummeRbund_on_RSQLite2.0

According to RSQLite 2.0, the following commands are been retired.
1. "RSQLite::make.db.names() is deprecated, please switch to DBI::dbQuoteIdentifier()."
2. "RSQLite::dbGetPreparedQuery() is deprecated, please switch to DBI::dbGetQuery(params = bind.data)."

In cummeRbund source code, the following files use "make.db.names":
1. database-setup.R
2. methods-CuffData.R

And the follwing file uses "dbGetPreparedQuery":
1. database-setup.R



In files using "make.db.names", I simply replace the command with "dbQuoteIdentifier" as RSQLite 2.0 suggested.
In the file "database-setup.R", the function "bulk_insert" is been re-writed to use "dbExecute" for insertion of the given data frame.



Installation:
1. git clone https://github.com/shiauck/cummeRbund_on_RSQLite2.0.git
2. tar -czvf cummeRbund.tgz cummeRbund_on_RSQLite2.0
3. R CMD INSTALL --no-lock cummeRbund.tgz


