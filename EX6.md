# Ex. No: 6 Creating Cursors using PL/SQL

### AIM:
To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
### Create employee table
```
CREATE TABLE e6 (emp_id number,emp_name char(20),emp_dept char(20),emp_salary number);
```
### Inserting the values:
```
INSERT INTO e6 VALUES(1,'ABINAYA','HR',70000);
INSERT INTO e6 VALUES(2,'AAROHI','MD',95000);
INSERT INTO e6 VALUES(3,'RAHUL','Finance',80000);
```

### PLSQL Cursor code
```
SQL> set serveroutput on
SQL>  declare
      cursor e6_cursor is
      select emp_id, emp_name,emp_dept,emp_salary
      from e6;
      emp_id number;
      emp_name varchar(90);
      emp_dept varchar(90);
      salary number;
      emp_salary number;
      begin
      open e6_cursor;
      loop
      fetch e6_cursor into emp_id,emp_name,emp_dept,emp_salary;
      exit when e6_cursor%notfound;
      dbms_output.put_line('Employee ID: '||emp_id);
      dbms_output.put_line('Employee Name: '||emp_name);
      dbms_output.put_line('Department: '||emp_dept);
      dbms_output.put_line('Salary: '||emp_salary);
      end loop;
      close e6_cursor;
      end;
      /

```
### Output:
![db6](https://github.com/abinayasangeetha/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/119393675/b668ffb2-9c5d-440e-a3f5-87929c4bf2be)
![DB 6 1](https://github.com/abinayasangeetha/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/119393675/d1452853-b971-41a7-a1cb-7f4a6c65a931)

### Result:
To create a cursor using PL/SQL is executed successfully.
