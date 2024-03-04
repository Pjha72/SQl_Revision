# Lec - 01 : Introduction of Database Management System

## Database System : fb ka apna ek database system .....

### There are two terms in Database System

#### 1. Database : It is a collection of Related Data.

##### 1.1 Structured : Data store in a any particular structure => RDBMS

             1.1.1 IRCTC Data
             1.1.2 University Data

##### 1.2 Unstructured : Data store in a not any particular structure

             1.2.1 Web Pages

#### 2. DBMS : To perform a CRUD Operations, to use DBMS System

              2.1 SQL Server
              2.2 Oracle
              2.3 MySql
              2.4 DB2

# Lec - 02 : File System Vs DBMS

## File Systems                   

### 1. It requires Attributes        
### 2. Concurrnecy - no any protocol
### 3. Security - No any role based access control   
### 4. Redundancy - More dulicate value persent
  
## DBMS

### 1. Not requires any attribute
### 2. Concurrencey - With protocol
### 3. DBMS Provides role based access control
### 4. Redundancy - Less dulicate value persent

# Lec - 04 : 2 tier and 3 tier Architecture
### 2 tier : It is also known as Client-Server Architecture. So in this Architecture there are two layres i.e Client Layer and Database Layer. Client runs the Query on the Interface after that Interface send the Query on the server, and Server take the required data from the Database. Then send to the Client.Example : IRCTC, Bank(Physically) 

### Advantage : 
#### 1. Maintence is easy
### Disadvantage
#### 1. Scalability is less
#### 2. Security is less

3-tier Architecture : In this Architecture there are three layers i.e Client Layer, Business Layer, Data Layer. Client donot Communicate directly to Data Layer.
Client Send the Query to the Business Layer. Business Layer Convert this Query to Machine Understanable Query then send to the Data Layer. And Data Layer sends the data to the Business layer then send to the Client Layer.

Advantage : 
1. Security is High
2. Scalability is High

Disadvantage : 
Maintence is High

# Lec - 05 : Schema
Schema : It is a Logical Representation of Database.
It is define in the Data Definition Language.

