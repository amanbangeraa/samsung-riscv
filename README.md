<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>

<h1>RISC-V Talent Development Program</h1>

<p>The project is based on the RISC-V Talent Development Program.</p>

<hr>

<details>
  <summary>Task00 - Installation</summary>
  <p>not updated yet</p>
</details>

<hr>

<details>
  <summary>Task01 - Development of C Program</summary>

  <h3>Step 01: Fire up the terminal</h3>
  <pre><code>vsduser@vsduser-VirtualBox:~$</code></pre>

  <h3>Step 02: Change the directory to home</h3>
  <pre><code>cd</code></pre>

  <h3>Step 03: Open leafpad</h3>
  <pre><code>leafpad sum1ton.c &</code></pre>

  <h3>Step 04: Write the code</h3>
  <pre><code>#include<stdio.h>
int main(){
    int sum = 0, n = 100, i;
    for(i=0; i<=n; i++){
        sum+=i;
        printf("The sum from 1 to 100: %d \n", sum);
    }
    return 0;
}</code></pre>

  <h3>Step 05: Save the file and run the following prompt in the terminal to compile the program</h3>
  <pre><code>gcc sum1ton.c</code></pre>

  <h3>Step 06: Run the program</h3>
  <pre><code>./a.out</code></pre>
  <img src="https://github.com/amanbangeraa/samsung-riscv/blob/main/Task01/01-output.png?raw=true" alt="run">

  <hr>

  <h3>Step 07: Compile the program in Assembly</h3>
  <pre><code>riscv64-unknown-elf-gcc -01 -mabi=lp64 -march=rv64i -o sumiton.o sumiton.c</code></pre>
  <img src="https://github.com/amanbangeraa/samsung-riscv/blob/main/Task01/04-assembydump.png?raw=true" alt="assembly">

  <hr>

  <h3>Step 08: Disassemble the sumiton.o object file for the RISC-V 64-bit architecture, displaying its assembly instructions</h3>
  <pre><code>riscv64-unknown-elf-objdump -d sumiton.o</code></pre>

  <hr>

  <h3>Step 09: Disassemble the sumiton.o object file for the RISC-V 64-bit architecture, enabling easy scrolling</h3>
  <pre><code>riscv64-unknown-elf-objdump -d sumiton.o | less</code></pre>
  <img src="https://github.com/amanbangeraa/samsung-riscv/blob/main/Task01/05-assemblydumpless.png?raw=true" alt="step09">

  <hr>

  <h3>Step 10: Search for the main section</h3>
  <img src="https://github.com/amanbangeraa/samsung-riscv/blob/main/Task01/06-searchmain.png?raw=true" alt="obj2">

  <hr>

  <h3>Step 11: Observe the beginning and final bits, then count the number of instructions executed using a programmable calculator and verify with the code</h3>
  <img src="https://github.com/amanbangeraa/samsung-riscv/blob/main/Task01/08-bitcalculation2.png?raw=true" alt="obj2">

</details>

</body>
</html>
