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

# Lec - 06 : Three Level Schema
Main motive for this schema is `Data Independence`.
There are Three Level : External Schema(View Level) => Conceptual Schema(Logical Level) => Physical Schema(Physical Level) => Database(Disk)
Provide the Abstraction.

# Lec - 07 : Data Independence OR Data Abstraction
Hide the Logic or Data From the Users.
There are Two Types of Data Independence.
1. Logical Data Independence : View Level to Conceptual Level
2. Physical Data Independence : Conceptual Level to Physical Level

# Lec - 08 : Integrity Constraints in Database
Integrity Constraints are rules defined in a database to maintain accuracy, consistency, and reliability.
Types of Integrity Constrauints
1. Domain Constraints: Attributes(int age, Char name ...)
2. Entity Integrity Constraints: Related To Primary Key(Not NULL)
3. Referential integrity Constraints: Foreign Key
4. Key Constraints: Unique Attribute

# Lec - 09 : Candidate Key
Key : It is a Normal Attributes
Use of Key : To Uniquely Identify any Two tuples in Table
It is a set of or collection of unique attributes in table.

# Lec - 10 : Primary Key(Unique + NOT NULL)
It is a Unique and Not NULL.

# Lec - 11 : Foreign Key
It is an attribute or set of attributes that references to Primary Key of same table or another table(relation).
It maintains the Referential Integrity
Base Table(Referenced Table) + Referncing Table
Syntax : create table Course(c_id varchar(10), c_name varchar(20), roll_no int reference Student(roll_no));
In one table more than one foregin key is persent but Primary Key is only one.

Refernced Table
1. Insert - No Violation
2. Delete - May Cause Violation(On Delete Cascade, On Delete Set NULL)
3. Update - May Cause Violation(On Update Cascade)

Referencing Table
1. Insert - May Cause Violation
2. Delete - Will Not Cause Any Violation
3. Update - May Cause Violation

# Lec - 12 : Super Key
A super key is a combination of all Possible attributes which can uniquely identify two tuples in a table.
Super set of any candidate key is Super Key.
Ex : (roll_no, age, name)
Q: IF R(A1,A2,A3,...An) then how many super keys are possible.
if A1 is a Candidate Key & A3,A2 are candidate key.
Soln : Take a Power Set of R
Total no of Possibility = 2^n
1. A1 is candidate key then super key is 2^n-1.Boz left the A1 then remaining element is n-1. Then choice is 2^n-1.
2. A3,A2 is candidate key then super key is 2^n-1+2^n-1-2^n-2

# Lec - 13 : Entity Relationship Model(ER Model)
Entity : Any Object that have Physical Existence.
Ex : Student(RollNo, age, address) => Entity Type OR Schema
Relationship : Make a association or Relationship between Two Entity.
Ex: Student--->Study(Relationship)<---Course
Representation : 
1. Entity => Squre
2. Attribute-Type => Eclispe
3. Relationship => Diamond

# Lec - 14 : Types of Attributes
1. Single Vs MultiValued
Single : Only one valued of Attributes
Represent : Single Eclispe
Ex : Reg.No
MultiValued : Multiple OR More than one Valued Attributes
Representation : Double Eclispe
Ex : Address => Permanant OR Correspondese

2. Simple Vs Composite
Simple : It cannot further divide
Representation : 
Ex : Age
Composite : It Can Futher Divide into two Valued Attributes
Representation : 
Ex : Name => first_name + last_name

3. Stored Vs Derived
Stored : Cannot derived
Ex : DOB
Derived : It Can derived attribute
Representation : Dotted Eclispe
Ex : age => DOB + Today

4. Key Vs Non-Key Attributes
Key : Which is used to uniquely identify the attributes
Representationm : Underline
Ex: Reg.No
Non-key : Cannot identify Unique

# Lec - 15 : Degree of Relationship(Cardinality)
Make a Association between two entity i.e relationship.
1. One-to-One : Where the two entity is connected in One-to-One Association.
Ex : Employee --> Works <--- Department
Primary key in Works table is `Either E_id OR D_id`. There are Final two table in One-To-One Rwlationship.
2. One-to-Many : Here One customer can give many order i.e the example.
Ex: Customer ---> Gives <--- Order
The name of relationship attribute is `Descriptive Attribute`.
Primary key : Only one primary key(`Order_No`) in Relationship table.
Many vale side ke table ke primary key hii Relationship table ka primary key hota hai.
Reduce no of tables in `One-to-Many` i.e 3 convert to 2 in many side.
3. Many-to-One : Here Many customer can give one order i.e the example.
Ex: Customer ---> Gives <--- Order
The name of relationship attribute is `Descriptive Attribute`.
Primary key : Only one primary key(`Cust_Id`) in Relationship table.
Many vale side ke table ke primary key hii Relationship table ka primary key hota hai.
Reduce no of tables in `Many-to-One` i.e 3 convert to 2 in many side.
4. Many-to-Many : Here Many Student Study Many Course i.e the example.
Ex: Student ---> Study <--- Course
Primary key in Refrencing Or Relationship table is `Roll_No & C_id` (Composite key).
Reduce no of table is not possible.



