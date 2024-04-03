# Ex. No: 7 PL/SQL program -BIGGEST OF THREE NUMBERS  
### DATE: 
### AIM: To create PL/SQL program to find biggest of three numbers.

### ALGORITHM:
1. Declare the variable a, b, c and assign value in Declare section.
2. begin the section
3. Find biggest of three numbers 
4. 5. Display the result 
6. End the begin section.

### Program:
```

DECLARE
  
  num1 NUMBER := 10; 
  num2 NUMBER := 20; 
  num3 NUMBER := 15;
  biggest NUMBER;
BEGIN
  
  IF num1 >= num2 AND num1 >= num3 THEN
    biggest := num1;
  ELSIF num2 >= num1 AND num2 >= num3 THEN
    biggest := num2;
  ELSE
    biggest := num3;
  END IF;


  DBMS_OUTPUT.PUT_LINE('The biggest number is: ' || biggest);
END;

```

### Output:
![281376927-4c1b84ec-8d83-493c-88d1-419c03a8c919](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/a6521964-917c-4618-9b7a-0d8f7ec82147)



### Result:
Thust the program was performed sucessfully.
