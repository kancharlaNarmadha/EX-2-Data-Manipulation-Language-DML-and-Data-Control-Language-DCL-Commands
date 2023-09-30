# EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands
# AIM:
To create a manager database and execute DML queries using SQL.

DML(Data Manipulation Language)
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
# List of DML commands:
INSERT: It is used to insert data into a table.
UPDATE: It is used to update existing data within a table.
DELETE: It is used to delete records from a database table.
# Create the table as given below:
```
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
# insert the following values into the table
```
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```
# Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

# QUERY:
```
update manager set salary=salary+(salary*0.10);
```

# OUTPUT:

 ![image](https://github.com/kancharlaNarmadha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559316/95ee890b-6fde-4575-8a63-7ab72df50560)


# Q2) Delete the records from manager table where the salary less than 2750.

# QUERY:
```
delete from manager where salary<2750;
```
# OUTPUT:
![image](https://github.com/kancharlaNarmadha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559316/5828daf8-4ba9-4637-ac8b-076e663d466c)



# Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)

# QUERY:
```
select ename as "Name",salary*12 as "Annual salary" from manager;
```
# OUTPUT:

![image](https://github.com/kancharlaNarmadha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559316/8a92f16a-c3ec-460d-8865-291fafc92bab)

# Q4) List the names of Clerks from emp table.

# QUERY:
```
select ename from manager where designation='clerk';
```
# OUTPUT:
![image](https://github.com/kancharlaNarmadha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559316/21a28f72-7662-4023-be2e-57e1b1a9ea77)


# Q5) List the names of employee who are not Managers.

# QUERY:
```
select ename from manager where designation <> 'manager';
```
# OUTPUT:
![image](https://github.com/kancharlaNarmadha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559316/5f518933-1bdd-493b-be97-9130d296d4f9)


# Q6) List the names of employees not eligible for commission.

# QUERY:
```
select ename from manager where commission=0;
```
# OUTPUT:
![image](https://github.com/kancharlaNarmadha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559316/30559437-35e1-4db7-b2e7-6dfe13c992f9)


# Q7) List employees whose name either start or end with ‘s’.

# QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```
# OUTPUT:

![image](https://github.com/kancharlaNarmadha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559316/f019612e-a0f9-46f6-a041-b5d09ffa12a1)

# Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.

# QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```
# OUTPUT:
![image](https://github.com/kancharlaNarmadha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559316/165eabb5-0789-47ce-9a4a-2143b10b8ac2)


# Q9) List the Details of Employees who have joined before 30 Sept 81.

# QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```
# OUTPUT:
![image](https://github.com/kancharlaNarmadha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559316/3fed1b7a-9f54-47a5-839b-5fb5ef1baa3f)


# Q10) List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.

# QUERY:
```
 select ename,deptno,salary from manager order by deptno asc,salary desc;
```
# OUTPUT:
![image](https://github.com/kancharlaNarmadha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559316/7501c034-1816-4f8b-bf4f-00486ac0f554)


# Q11) List the names of employees not belonging to dept no 30,40 & 10

# QUERY:
```
select ename from manager where deptno not in (30,40,10);
```
# OUTPUT:

![image](https://github.com/kancharlaNarmadha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559316/5e1df65d-4b23-4de7-a4e2-076455133bf8)

# Q12) Find number of rows in the table EMP

# QUERY:
```
 select count(*) from manager;
```
# OUTPUT:
![image](https://github.com/kancharlaNarmadha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559316/ba1e8af9-d17c-4acc-8602-f5c5895caefc)


# Q13) Find maximum, minimum and average salary in EMP table.

# QUERY:

# MAXIMUM:
```
select max(salary) from manager;
```
# OUTPUT:
![image](https://github.com/kancharlaNarmadha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559316/068a2ca3-c84f-489e-b090-fde0071d9b47)


# MINIMUM:
```
select min(salary) from manager;
```
# OUTPUT:

![image](https://github.com/kancharlaNarmadha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559316/ad4ef64c-8808-42e8-8fae-29020a676abe)

# AVERAGE:
```
select avg(salary) from manager;
```
# OUTPUT:

![image](https://github.com/kancharlaNarmadha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559316/7345a527-1239-4faa-b119-132287c67c85)

# Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

# QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```
# OUTPUT:
![image](https://github.com/kancharlaNarmadha/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119559316/ef699245-aa3e-4d72-bf46-89c4022253d8)


# Result:
To create a manager database and execute DML queries using SQL is executed successfully.
