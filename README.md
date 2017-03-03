### Hautelook Way of Testing:

### MySQL
   * Tesing MySQL backups and testing your application using small set of test data (fixture data) is very essential, at hautelook we have      both of this process. 
   
##### Database Refresh
   * We have our daily production MySQL backups, that we use everyday to load into staging database that way it can be used for staging        data and also we can verify that daily backup works and has no issues.
   * We call it a refresh process, we carefully make sure all PII related data are either encyrpted, i.e. memeber info., billing,              shipping, emails, etc or those tables are excluded that make use secure to use those data and we compliance with PCI.
   * Test database has very similar setup as production databases and have same replication process gives us advantage of testing schema,      sproc changes on staging befor it makes it to production.
   
##### Fixture Database aka Test Database
   * A Solution created in house, can setup test database with all needed data within 30 seconds or less. Contains just enough data and        all latest schema, sprocs, triggers in order to run local, QA and automated testing environment against this database.
   * This database uses recurrsion when loading data and finds the tables with no dependencies and installs them first that way we can          test table constraints and we do not need to turn off the foreign key constraints.
   * The Test database contains all different data set which allows to do continuous integration and automation test never fails due to        data errors and can be reset back in between the tests or before new tests are started.

### API Testing
