Alter Table
==============================================

```
BEGIN TRANSACTION;

ALTER TABLE TableName RENAME TO TableName_Old;

CREATE TABLE "TableName" (
	"Column1"	  INTEGER NOT NULL PRIMARY KEY,
	"Column2"	  INTEGER NOT NULL DEFAULT 0,
    "Column3"     DATETIME NULL,
	"ColumnNew"	  INTEGER NOT NULL DEFAULT 0,
    FOREIGN KEY(Column1) REFERENCES Table2(Id) ON DELETE CASCADE
);

INSERT INTO TableName SELECT * FROM TableName_Old;

DROP TABLE TableName_Old;

COMMIT;
```
