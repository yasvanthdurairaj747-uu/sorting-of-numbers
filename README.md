# SORTING OF NUMBERS
### AIM
To write and execute an Assembly Language Program for sorting data in Ascending and  descending order using 8051 microcontroller on Keil software.


### APPARATUS REQUIRED
- Personal Computer  
- Keil µVision software  


### ALGORITHM (ASCENDING ORDER)

1. Load number of elements from memory location 30H into R7.  
2. Decrement R7 (Outer loop count = N−1).  
3. Initialize pointer R0 to 40H (starting address).  
4. Load R6 with N−1 (inner loop counter).  
5. Load first element into A.  
6. Load next element into B.  
7. Compare A and B.  
8. If A > B → swap them.  
9. Repeat inner loop until R6 = 0.  
10. Repeat outer loop until R7 = 0.  
11. Stop execution.    


### PROGRAM (ASCENDING ORDER)

```asm
ORG 0000H
       MOV R7,30H     
       DEC R7         

LOOP1: MOV R0,#40H
       MOV R6,30H
       DEC R6

LOOP:  MOV A,@R0
       INC R0
       MOV B,@R0
       CJNE A,B,NEXT

NEXT:  JC DOWN

       MOV @R0,A
       DEC R0
       MOV @R0,B
       INC R0

DOWN:  DJNZ R6,LOOP
       DJNZ R7,LOOP1

HERE:  SJMP HERE

END
```
#### BEFORE SORTING IN ASCENDING ORDER

##### Entering the number of elements to be stored in 30H    
<img width="510" height="181" alt="image" src="https://github.com/user-attachments/assets/b887ed8a-3bfe-4a96-9d80-1acda323367b" />   

##### Entering the elements in 40H      
<img width="502" height="188" alt="image" src="https://github.com/user-attachments/assets/3f0b0b84-187d-468f-b90b-1a3f22239ee9" />  

### OUTPUT (ASCENDING ORDER)
  
##### Sorted array in ascending order  
 <img width="631" height="463" alt="image" src="https://github.com/user-attachments/assets/b67edb49-c067-4d3b-9732-8c469f3e45fc" />  
 
##### Memory Window 
 <img width="473" height="205" alt="image" src="https://github.com/user-attachments/assets/462f03cb-97a8-44dd-b63a-5592be068679" />
 
---
### ALGORITHM (DESCENDING ORDER)
1. Load number of elements from memory location 30H into R7.  
2. Decrement R7 (outer loop = n−1 passes).  
3. Initialize pointer R0 to starting address 40H.  
4. Load R6 with n−1 (inner loop counter).  
5. Load first element into accumulator A.  
6. Increment pointer and load next element into B.  
7. Compare A and B.  
8. If A < B, swap the two elements.  
9. Repeat inner loop until R6 = 0.  
10. Repeat outer loop until R7 = 0.  
11. Stop the program.  

### PROGRAM (DESCENDING ORDER)

```asm
ORG 0000H
       MOV R7,30H     ; Load number of elements
       DEC R7         ; Outer loop = n-1
	   
LOOP1: MOV R0,#40H
       MOV R6,30H
       DEC R6

LOOP:  MOV A,@R0
       INC R0
       MOV B,@R0
       CJNE A,B,NEXT

NEXT:  JNC DOWN       ; If A > B ? correct order ? skip
       ; Swap when A < B
       MOV @R0,A
       DEC R0
       MOV @R0,B
       INC R0

DOWN:  DJNZ R6,LOOP
       DJNZ R7,LOOP1

HERE:  SJMP HERE

END
```
#### BEFORE SORTING IN DESCENDING ORDER

##### Entering the number of elements to be stored in 30H    
 <img width="504" height="159" alt="image" src="https://github.com/user-attachments/assets/ca376b06-5283-4c76-897a-0607c9edee3f" />


##### Entering the elements in 40H      
<img width="504" height="158" alt="image" src="https://github.com/user-attachments/assets/3996e407-ccbd-4920-a01e-d9d99b573542" />


### OUTPUT (DESCENDING ORDER)
  
##### Sorted array in descending order  
 <img width="640" height="458" alt="image" src="https://github.com/user-attachments/assets/84830f13-9c77-4afc-8a99-486e32f0efc2" />

 
##### Memory Window
<img width="476" height="161" alt="image" src="https://github.com/user-attachments/assets/35e348cd-b5d7-41ab-b084-2f08e334df08" />

---
### RESULT:
Thus the sorting of given data was done using 8051 keil software.
