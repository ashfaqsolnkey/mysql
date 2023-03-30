# SQL 

## How to create the student table in MySQL?

```
create table student (
	`studentId` integer primary key auto_increment not null,
	`Name` varchar(40) not null,
	`fatherName` varchar(40),
	`course` varchar(40) not null,
	`email` varchar(40) not null,
	`mobile` bigint,
	`pincode` integer  not null,
	`city` varchar(155)  not null,
	`state` varchar(155)  not null,
	`country` varchar(155)  not null,
	`modeCo` enum ('online' , 'offline'),
	`minor` enum ('true' , 'false')
	);
```

## How to create the fees table in MySQL?

```
CREATE TABLE `fees` ( 
 `feeid` integer  PRIMARY KEY NOT NULL AUTO_INCREMENT, 
 `amount` bigint,
 `month` varchar(255),
 `studentId` integer
);
```

## How to insert a new fee record into the fees table for a particular student?

```
By studentid field 

insert into fees ( amount ,month, studentId)
values(  3000  ,'feb' , 4);
```

## How to update a student record in the student table?

```
update student  set  fatherName ='etc'  where studentId = 4; 
```

## How to update a fee record in the fees table?

```
update fees  set  amount = 4000  where studentId = 4; 
```

## How to select all the records from the fees table?

```
select * from fees;
```

## How to select a particular student record from the student table?

```
select * form student where studentId = 1;
```

## How to select all the fee records for a particular student from the fees table?

```
select * from fee where studentId = 1;
```

## How to get the total number of students in the student table?

```
select count(*) from student;
```

## How to get the sum of all the fees paid by a particular student?

```
select sum(amount) from fees;
```

## How to get the average fee paid by all the students?

```
select avg(amount) from fees;
```

## How to get the student record with the highest mobile number in the student table?

```
select max(mobile) from student;
```

## How to get the fee record with the highest fee amount in the fees table?

```
select max(amount) from fees;
```

## How to get the list of all students who live in a city?

```
select city from student;
```

## How to get the list of all students who have paid fees for the month of 'February'?

```
select * from fees where month = "feb" and amount = is not null;
```

## How to get the list of all cities along with the count of students living in each city?

```
select address,count(studentId) from student group by address;
```

## How to get the list of all cities along with the count of students living in each city, where the count is greater than 1?
```
select address from student group by studntId having count(studentId)>=1;
```

## How to get the list of all students sorted by their names in ascending order?

```
select * from student order by Name;
```

## How to get the list of all students sorted by their mobile numbers in descending order?

```
select * from student order by mobile desc;
```

## How to get the list of all fees records sorted by the fee amount in descending order?

```
select * from fees order by amount desc;
```

## How to get the list of all fees records sorted by the fee amount in descending order, for a particular student?

```
select * from fees where studentId = 2 order by amount desc;
```
