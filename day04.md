# Day 4 Learning:
## transaction
- Its a sequence of operation  like INSERT,UPDATE,DELETE what excute as single unit of work.
- its start with BEGIN TRANSACTION it actually start the operation but it did not make any change but when u run commit operation then it permanately  make change before commit if there is any mistake u can use ROLLBACK to undo.

- Example

BEGIN TRANSACTION;
UPDATE ACCOUNTS
SET BALANCE =BALANCE-150
WHERE ACCOUNT_ID='A';

UPDATE ACCOUNTS
SET BALANCE =BALANCE+150
WHERE ACCOUNT_ID='B';

COMMIT;

## Try-Catch
- its used to handle run time error so that a database doesnot endup broken or half updated state .
- example 
BEGIN TRY
    BEGIN TRANSACTION;
    -- work
    COMMIT;
END TRY
BEGIN CATCH
    ROLLBACK;
END CATCH;

- it work like this 
Try --> Do the work 
Catch --> if anything fails rollback
RollBack--> undose all the change 

## Trigger
- Trigger is like "when i open the Door the bell automatically started to make sound"

- After trigger most commonly used 
AFTER INSERT
AFTER UPDATE
AFTER DELETE
- Example 

CREATE TRIGGER trg_AfterInsert
ON Accounts
AFTER INSERT
AS
BEGIN
    PRINT 'New account added';
END;


when some one insert a row succesfully in table name "Aaccount" the trigger automatically print the message