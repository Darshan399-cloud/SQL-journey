# MySQL Database Backup

## 1. What is Database Backup?

Database backup means creating a copy of database information
so that it can be recovered when the original data is lost.

## 2. Importance of Backup

1. Protects important business information.
2. Helps recover deleted records.
3. Protects against hardware failure.
4. Helps recover from accidental database changes.
5. Supports disaster recovery.
6. Reduces the risk of permanent data loss.

## 3. Types of Backup

### Full Backup
Creates a backup of the complete database.

### Incremental Backup
Stores changes made since the previous backup.

### Differential Backup
Stores changes made since the last full backup.

## 4. mysqldump

mysqldump is a MySQL command-line utility used to export
database structures and data into SQL files.

Example:

mysqldump -u root -p ecommerce_db > ecommerce_backup.sql

## 5. Table Backup

A specific table can also be backed up.

Example:

mysqldump -u root -p ecommerce_db products > products_backup.sql

## 6. Backup Best Practices

1. Take backups regularly.
2. Store backups in a safe location.
3. Keep multiple backup copies.
4. Protect backup files with proper permissions.
5. Test database restoration regularly.
6. Maintain backup schedules.
7. Keep an off-site backup copy.