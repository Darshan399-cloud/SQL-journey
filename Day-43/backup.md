# SQL Database Backup

A database backup is a copy of database data that can be used to restore the database if data is lost or damaged.

## Why Backup is Important?

Backups help protect data from:

- Accidental deletion
- Hardware failure
- Software problems
- Database corruption
- Human mistakes

## mysqldump

mysqldump is a MySQL command-line utility used to create database backups.

## Backup Database

mysqldump -u root -p company_db > company_db_backup.sql

After running the command, MySQL asks for the password.

The backup is stored in:

company_db_backup.sql

## Backup Specific Table

mysqldump -u root -p company_db employees > employees_backup.sql

## Backup Multiple Tables

mysqldump -u root -p company_db employees departments > tables_backup.sql

## Backup Structure and Data

A normal mysqldump backup can contain:

- CREATE TABLE statements
- INSERT statements
- Database structure
- Table data

## Important

Keep backup files in a safe location.

For important databases, maintain multiple backup copies.