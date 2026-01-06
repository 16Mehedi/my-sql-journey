# Stored Procedure
- Its a sql prepared code which we can write one time and then store and can use again and again we dont need to write code every time .It handle complex business logic,increase performance,reduce repeated code also secure database.

- example:
CREATE PROCEDURE find_id
@userid INT

AS
BEGIN
SELECT*FROM users WHERE userId=@userid;
END;

when we want we can call like 

EXEC find_id 1;

# IF EXISTS
- its a operator what can check any object is already exist in the database or not basically it saves from error Example : 
IF EXISTS (SELECT 1 FROM Student WHERE Marks<40)
BEGIN 
DELETE FROM student WHERE Marks<40;
END;

# User-Defined Functions
### (Scalar Function)
- Actually its a reusable function what can not modify database but have to return value or table Example: 

- Scalar Function 

CREATE FUNCTION dbo.getYearlysalary(@Monthly INT)
RETURN INT
AS
BEGIN
RETURN @Monthly * 12;
END;

Call
SELECT dbo.GetYearlySalary(5000);

- Table-Valued Function
CREATE FUNCTION dbo.ActiveUsers()
RETURNS TABLE
AS
RETURN (
    SELECT * FROM Users WHERE IsActive = 1
);


# IBAN
- Prevent payment errors,supports international banking
- MOD 97 Detect typing error

IBAN_numeric % 97 = 1  → VALID
IBAN_numeric % 97 ≠ 1 → INVALID
