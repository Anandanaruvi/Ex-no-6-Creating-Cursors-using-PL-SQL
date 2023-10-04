### Ex. No: 5 Creating Cursors using PL/SQL

### AIM: To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:

### Create employee table

 CREATE TABLE employd(
  2  empid NUMBER,
  3    empname VARCHAR(10),
  4    dept VARCHAR(10),
  5    salary NUMBER
  6  );

### PLSQL Cursor code
```
 set serveroutput on;
SQL>  DECLARE
  2   CURSOR employd_cursor IS
  3  SELECT empid,empname,dept,salary
  4      FROM employd;
  5      emp_id NUMBER;
  6       emp_name VARCHAR(50);
  7        emp_dept VARCHAR(50);
  8        emp_salary NUMBER;
  9   BEGIN
 10   OPEN employd_cursor;
 11   LOOP
 12  FETCH employd_cursor INTO emp_id, emp_name, emp_dept, emp_salary;
 13   EXIT WHEN employd_cursor%NOTFOUND;
 14    DBMS_OUTPUT.PUT_LINE('Employee ID: ' || emp_id);
 15   DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name);
 16   DBMS_OUTPUT.PUT_LINE('Department: ' || emp_dept);
 17  DBMS_OUTPUT.PUT_LINE('Salary: ' || emp_salary);
 18   END LOOP;
 19   CLOSE employd_cursor;
 20
 21   END;
 22  /

```
### Output:
![image](https://github.com/Anandanaruvi/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/120443233/56c4bdff-c542-4f67-9ef2-ef11407cc27c)

![image](https://github.com/Anandanaruvi/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/120443233/63a16d70-17a7-4a5d-95a4-536c7d1496ad)
)

### Result:

Thus, a cursor is created using PL/SQL.

