# SQL Database Restore

Database restore means recovering database structure and data from a backup file.

## Create Database

CREATE DATABASE company_db;

## Restore Database

mysql -u root -p company_db < company_db_backup.sql

The SQL commands stored in the backup file are executed in the database.

## Restore Specific Table Backup

mysql -u root -p company_db < employees_backup.sql

## Restore Using MySQL Command Line

mysql -u root -p

Then:

CREATE DATABASE company_db;

USE company_db;

SOURCE company_db_backup.sql;

## Important

Before restoring a backup, make sure you are using the correct database.

Restoring a backup can create tables and insert data into the selected database.

## Backup vs Restore

Backup:

Database 