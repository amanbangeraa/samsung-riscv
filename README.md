
# RISC-V Talent development Program

The project is based on the RISC V talent development program.


## Task00 - Installation

```bash
import Component from 'my-project'

function App() {
  return <Component />
}
```

## Task01 - Development of C program

### Step01: Fire up the terminal 
```bash
vsduser@vsduser-VirtualBox:~$ 
```

### Step02: change the directory to home
```bash
cd
```

### Step03: open leafpad  
```bash
leafpad sum1ton.c &
```

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

### Step05: Save the file and run the following prompt in terminal to compile the program 
```bash
gcc sum1ton.c
```

### Step05: run the program
```bash
./a.out
```

### Step07: Compile the program in Assembly
```bash

```

