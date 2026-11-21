# MySQL Database Restore

## 1. What is Database Restore?

Database restore means recovering database information
from a previously created backup file.

## 2. Importance of Restore

1. Recovers lost database information.
2. Restores accidentally deleted records.
3. Helps recover after database failure.
4. Supports disaster recovery.
5. Restores database structure and data.

## 3. Restore Using MySQL Command

mysql -u root -p ecommerce_db < ecommerce_backup.sql

## 4. Restore a Table

mysql -u root -p ecommerce_db < products_backup.sql

## 5. Restore Using MySQL Workbench

1. Open MySQL Workbench.
2. Connect to the MySQL server.
3. Open Server menu.
4. Select Data Import.
5. Choose Import from Self-Contained File.
6. Select the backup SQL file.
7. Select the target database.
8. Click Start Import.

## 6. Backup vs Restore

| Backup | Restore |
|--------|---------|
| Creates a database copy | Recovers database data |
| Used for data protection | Used for data recovery |
| Exports database information | Imports database information |
| Creates backup files | Uses backup files |

## 7. Best Practices

1. Verify backup files before restoration.
2. Restore into the correct database.
3. Test restoration regularly.
4. Keep original backup files safe.
5. Avoid restoring over production data without approval.