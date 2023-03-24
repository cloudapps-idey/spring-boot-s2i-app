mysql-container-setup

In this directory the files are helper file to initialize an mysql container inside an openshift 
namespace. Files description:

init-db-container.sh  : Creates a 'mysql' container 
populate-db.sh        : Populates the 'bookstore' database
create-book-table.sql : Creates a table under bookstore database named 'book'
insert-book-data.sql  : populates the 'book' table with few row. 

===================================================================
             Setup manually
==================================================================

1. init-db-container.sh
2. Obtaine the pod name
3. copy the sql files to the mysql container 
4. Run the files inside mysql container

====================================================================
              Setup usng scripts
====================================================================
  
1. Run  the following script to create an ephemeral mysql container

   init-db-container.sh

2. oc get pod

3. Copy the pod name and set the value in the populate-db.sh/bat
     mpod=mysql-1-cj68h

4. populate-db.sh

5. if issue with grant then
    oc rsh mysql pod
        mysql -u root
        GRANT ALL PRIVILEGES ON *.* TO 'user1'@'%';


