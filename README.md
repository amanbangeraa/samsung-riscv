
# RISC-V Talent development Program

The project is based on the RISC V talent development program.
***
## 🚀 About Me 

Name: Aman Bangera <br>
College: Sahyadri College of Engineering & Manangement<br>
Contact me: atharvbangera2005@gmail.com / aman.ec23@sahyadri.edu.in<br>

## 🔗 Links
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/amanbangera?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app)


---
<details>
  <summary>Task01 - Development of C program</summary>

---
### Step01: Fire up the terminal 
```bash
vsduser@vsduser-VirtualBox:~$
```

---

### Step02: change the directory to home
```bash
cd
```

---

### Step03: open leafpad  
```bash
leafpad sum1ton.c &
```

---

### Step04: Write the code
```c
#include<stdio.h>
int main(){
    int sum = 0, n = 100, i;
    for(i=0; i<=n; i++){
        sum+=i;
        printf("The sum from 1 to 100: %d \n", sum);
    }
    return 0;
}
```

---

### Step05: Save the file and run the following prompt in terminal to compile the program 
```bash
gcc sum1ton.c
```

---

### Step05: run the program
```bash
./a.out
```
![run](https://github.com/amanbangeraa/samsung-riscv/blob/main/Task01/01-output.png?raw=true)

---

### Step07: Compile the program in Assembly
```bash
riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv6 4i-o sum1ton.o sum1ton.c
```
![assembly](https://github.com/amanbangeraa/samsung-riscv/blob/main/Task01/04-assembydump.png?raw=true)


---

### Step08: disassemble the sum1ton.o object file for the RISC-V 64-bit architecture, displaying its assembly instructions
```bash
riscv64-unknown-elf-objdump -d sum1ton.o
```

---

### Step09: disassemble the sum1ton.o object file for the RISC-V 64-bit architecture, enable easy scrolling
```bash
riscv64-unknown-elf-objdump -d sum1ton.o | less
```
![step09](https://github.com/amanbangeraa/samsung-riscv/blob/main/Task01/05-assemblydumpless.png?raw=true)


---

### Step10: Search for the main section
![obj2](https://github.com/amanbangeraa/samsung-riscv/blob/main/Task01/06-searchmain.png?raw=true)


---

### Step10: observe the begining and final bit and count the number of instructions executed using a programmable calculator and verify with the code
![obj2](https://github.com/amanbangeraa/samsung-riscv/blob/main/Task01/08-bitcalculation2.png?raw=true)

### Step 12: Compare the results with optimizations (-Ofast)
```bash
riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv6 4i-o sum1ton.o sum1ton.c
```

Once you have the optimized object file, disassemble it again:
```bash
riscv64-unknown-elf-objdump -d sum1ton.o | less
```
Then, perform the same search for main and instruction count calculations to compare with the non-optimized version.

</details>
