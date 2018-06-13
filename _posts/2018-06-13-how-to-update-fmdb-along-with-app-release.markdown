---
layout: post
title:  "How to migrate FMDB along with new App releases"
date:   2018-06-13 23:00:00 +0800
categories: Collection Base FMDB
---
* ### How to create a unique id in iOS with Swift
  ```
  let uuid = UUID().uuidString
  ```
* ### How to migrate FMDB along with new App releases
  * Tool: [FMDBMigrationManager](https://github.com/layerhq/FMDBMigrationManager)
  * How: Treat your database like git repository, add modifications like commits, and apply commits to the current state
  * Steps:
    * install FMDBMigrationManager with pod
    * New a FMDBMigrationManager linked to your database
    * Create a version table with FMDBMigrationManager
    * As your apps release, new migrations are need
    * New migrate objects that confirm FMDBMigrating
      * Implement methods in the protocol
      * Version and progress closure is the most important part
      * Which determine the order of migrations and what will be done
    * Migrate to latest version
    ```
    //create manager
    FMDBMigrationManager *manager = [FMDBMigrationManager managerWithDatabaseAtPath:@"path/to/your/DB.sqlite" migrationsBundle:[NSBundle mainBundle]];
    //create table, check existed before create
    BOOL success = [manager createMigrationsTable:&error];
    //New objects confirm to FMDBMigrating
    //Add to manager
    [manager addMigrations:[#yourMigrations]]
    //migrate
    BOOL success = [manager migrateDatabaseToVersion:UINT64_MAX progress:nil error:&error];
    ```
    * As your app continue releases, just new FMDBMigrating objects and add them to manager
