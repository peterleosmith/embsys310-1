**Question 1**\
**a)** In order to swap the pointers, the main function has to pass the **address of the pointers** so that the swap function can swap the pointers variables and not the values that they point to. 

**b)** When SwapPointer function is called, R0 and R1 register values hold the **addresses** of the xPtr and yPtr respectively. writing to the register without using bit banding, the compiler produced 4 instructions as follows:\
*i)* first instruction to load the targeted register address into R0\
*ii)* second instruction for loading the value pointed to by the R0 address into R1 register\
*iii)* third instruction for performing the OR operation and updating the R1 register with the new value\
*iv)* fourth instruction for writing/storing the value in R1 into the address pointed to by R0. 

The described instructions above are captured in the image below:

![Bit Banding Vs No Bit Banding](https://github.com/ftoufaili/embsys310/blob/main/Assignment04/Images/BitBandingVsNoBitBanding.jpg)


<br/>**Question 2**\
**a)** The calling function func2 passes the values to the called function func1 by loading the value of these values in R0 through R3 registers as captured in the image below. Since we're passing more varaibles that registers R0 through R3 can hold, the 5th value was stored in memory that is pointed to by the Stack Pointer SP as can be seen in the image below.\
**b)** Before calling the function func1 with multiple arguments, the compiler created extra code to update the link register before calling Branch to Label (i.e. BL) instruction to change the value of the PC register.

![Passing Arguments By Value](https://github.com/ftoufaili/embsys310/blob/main/Assignment04/Images/PassingVariablesByValue.JPG)

**c)** With the multiple list of arguments, the compiler generated code to retrieve the 5th argument value that is stored in the SP register before adding all the values