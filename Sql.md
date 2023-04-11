## Create database

```
CREATE DATABASE instituteMangement;
```


## USE database

```
USE instituteMangement;
```


## Create Students Table

```
    create table student (
	`studentId` integer primary key auto_increment not null,
	`Name` varchar(40) not null,
	`FatherName` varchar(40),
	`Email` varchar(40) not null,
	`Mobile` bigint,
	`Address` varchar(155)  not null,
    `AdmissionDate` date
	);
```


## Create Employee Table

```
    create table Employee (
	`EmployeeId` integer primary key auto_increment not null,
	`Name` varchar(40) not null,
	`employeetype` varchar(40)
	);
```



## Create Course Table

```
	create table Course (
    `CourseId`  integer primary key auto_increment not null,
	`Name` varchar(55) not null,
    `Fee` bigint not null,
    `StartDate` date ,
    `EndDate` date,
    `Time` time
    );
```



## Create Fees Table

```
	create table Fees (
	`FeesId` integer primary key auto_increment not null,
    `Amount` bigint not null,
    `Month` date not null,
    `StudentId` integer,
    CONSTRAINT F_K_StudentId FOREIGN KEY (studentId)
	REFERENCES student(studentId)
	);
```

## Create Test Table

```
   create table Test (
	`TestId` integer primary key auto_increment not null,
    `Testname` varchar(155) not null,
    `Passingmarks` integer not null,
    `Totalmarks` integer not null,
    `testdate` date,
	CONSTRAINT F_K_TestId FOREIGN KEY (TestId)
	REFERENCES student(studentId)
	);
```

## Create Result Table

```
 create table Result (
	`ResultId` integer unsigned auto_increment,
    `TestId` integer  ,
    `StudentId` integer  ,
    `Obtainedmarks` integer not null,
    `Result`enum('Pass','Fail') not null,
    primary key (ResultId,TestId,StudentId )
	);
```


## Create StudentCourse Table

```
 create table StudentCourse (
	`StudentCourseId` integer unsigned auto_increment,
    `StudentId` integer UNSIGNED ,
    `CourseId` integer UNSIGNED ,
    primary key (StudentCourseId,CourseId,StudentId)
	);
```






## Create EmployeeType Table

```
 create table EmployeeType (
    `EmployeeTypeId` integer primary key auto_increment not null,
    `employeeType` varchar(155) not null,
    CONSTRAINT F_K_EmployeeTypeId FOREIGN KEY (EmployeeTypeId)
	REFERENCES Employee(EmployeeId)
    );
```




## Create Salary Table

```
    create table Salary(
    `SalaryId` integer unsigned auto_increment not null,
    `amount`bigint not null,
    `month` varchar(155) not null,
    `EmployeeId` integer unsigned,
    primary key(SalaryId, EmployeeId)
    );
```



## Create Expenses Table

```
 create table Expenses(
    `ExpensesId`  integer primary key auto_increment not null,
    `ExpenseDetail` varchar(155) not null,
    `Amount` bigint not null,
    `Date` date
    );
```



## Create Address Table

```
 create table Address (
    `AddressId` integer unsigned auto_increment not null,
    `Colony` varchar(55) not null,
    `City` varchar(55) not null,
    `Pincode` integer not null,
    `State` varchar(55) not null,
    `StudentId` integer unsigned,
    primary key (AddressId , StudentId)
    );
```