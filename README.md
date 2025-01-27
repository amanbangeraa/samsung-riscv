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
<details>
  <summary>Task02 - Simulation with Spike</summary>
  <hr>
SPIKE is a simulator for the RISC-V architecture, allowing you to test and debug RISC-V programs without needing real hardware. It simulates a RISC-V processor and cache, and can run programs or even a Linux kernel. 

PK (Proxy Kernel) is a lightweight environment that helps run statically-linked RISC-V programs, acting like a simple operating system.

Test SPIKE through running a sample program (e.g. sum1ton.c) using both the gcc compiler and the RISC-V compiler. Confirm the two compilers produced the same output in executing the program on the simulator. 
  ### Step01: Compile and run the program
  ```bash
  cat sum1ton.c
  ```

  ```bash
  gcc sum1ton.c
  ```

  ```bash
  ./a.out
  ```
  ![c compilation](https://github.com/amanbangeraa/samsung-riscv/blob/main/Task02/00-cCompilation.png?raw=true)
  
  ---
  ### Step02: Compile with Optimization Level -O1
  ```bash
  riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
  ```
  ![o1](https://github.com/amanbangeraa/samsung-riscv/blob/main/Task02/01-O1compilation.png?raw=true)
  ---
  
  ### Step03: Generate an Object Dump
  ```bash
  riscv64-unknown-elf-objdump -d sum1ton.o | less
  ```
  
  ---
  ### Step04: Run the Program with the SPIKE Debugger
  ```bash
  spike -d pk sum1ton.o
  ```
  ![spike](https://github.com/amanbangeraa/samsung-riscv/blob/main/Task02/02-o1spike%20compilation.png?raw=true)
  ---

  ### Step05: Compile with Optimization Level -Ofast
  ```bash
  riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
  riscv64-unknown-elf-objdump -d sum1ton.o | less
  ```
  ![](https://github.com/amanbangeraa/samsung-riscv/blob/main/Task02/03-ofast.png?raw=true)
  ---
  ### Step06: Run the Program with the SPIKE Debugger
  ```bash
  spike -d pk sum1ton.o
  ```
  ![](https://github.com/amanbangeraa/samsung-riscv/blob/main/Task02/04-spikecompilation.png?raw=true)
  ### Step07: Compare Outputs
  O1 debug using Spike
  ![](https://github.com/amanbangeraa/samsung-riscv/blob/main/Task02/02-o1spike%20compilation.png?raw=true)
  ---
  Ofast debug using Spike
  ![](https://github.com/amanbangeraa/samsung-riscv/blob/main/Task02/04-spikecompilation.png?raw=true)
  Compare Outputs
  Once both versions (-O1 and -Ofast) have been compiled and run, compare the outputs from both compilers. You should check:
  
  Whether the outputs match between the GCC and RISC-V compiler.
  Any differences in the assembly code or execution behavior due to optimization.

</details>

<details>
  <summary> Task 03 </summary>
    
  ## 15 Unique RISC-V Instructions and their 32-bit Encodings:
  
## RISC-V Instructions and their Encodings

**addi sp, sp, -16** 
- Type: I-Type
- Encoding: 0010011 00000 00000 00000 1111111111110000

**sd ra, 8(sp)** 
- Type: S-Type
- Encoding: 0100011 00000 00100 11111 00000 000000001000

**li a5, 100** 
- Type: I-Type
- Encoding: 0010011 00000 00000 00101 0000000001100100

**addiw a5, a5, -1** 
- Type: I-Type
- Encoding: 1010011 00101 00000 00101 1111111111111111

**bnez a5, 10160** 
- Type: B-Type
- Encoding: 1100011 00101 00000 00000 0000000000001010

**lui a2, 0x1** 
- Type: U-Type
- Encoding: 0110111 00010 0000000000000000000000001

**addi a2, a2, 954** 
- Type: I-Type
- Encoding: 0010011 00010 00000 00010 0000001110111010

**li a1, 100** 
- Type: I-Type
- Encoding: 0010011 00000 00000 00001 0000000001100100

**lui a0, 0x1c** 
- Type: U-Type
- Encoding: 0110111 00000 000000000000000000011100

**addi a0, a0, 160** 
- Type: I-Type
- Encoding: 0010011 00000 00000 00000 0000000010100000

**jal ra, 1031c** 
- Type: J-Type
- Encoding: 1101111 00000 000000000000000000000000011111001100

**li a0, 0** 
- Type: I-Type
- Encoding: 0010011 00000 00000 00000 0000000000000000

**ld ra, 8(sp)** 
- Type: S-Type
- Encoding: 0100011 00000 00100 11111 00000 000000001000

**addi sp, sp, 16** 
- Type: I-Type
- Encoding: 0010011 00000 00000 00000 0000000000010000

**ret** 
- Type: R-Type
- Encoding: 1100111 00000 00000 00000 00000 1110011

</details>
<details>
  <summary>Task03</summary>
  
  ### 1. **Create a Directory**:
  ### 2. **Create the verilog files using touch command**
  ### 3. **locate the files created and paste the code from the <a href="https://github.com/vinayrayapati/rv32i/blob/main/?> repo </a>**
  Get the Verilog netlist from <a href="https://github.com/vinayrayapati/rv32i/blob/main/iiitb_rv32i.v">RISC-V Core Verilog Netlist.</a>
  Get the testbench from <a href="https://github.com/vinayrayapati/rv32i/blob/main/iiitb_rv32i_tb.v">Testbench for RISC-V Core.
  ### 4. **Compile the Files**
  ### 5. **run the files**
  ### 6. **Open the Waveform File in GTKWave**
  ### 7. **Add Signals to GTKWave:**
  ### 7. **Add Signals to GTKWave:**
</details>
<details>
  <summary>Task05: Project Overview</summary>
  
  ### BlueSense Automation System
  
  The BlueSense Automation System is an IoT project designed to automate home appliances and environmental monitoring using Bluetooth and DHT sensors. The system uses a RISC-V SoC chip to control a relay module based on Bluetooth commands, alongside gathering temperature and humidity data from a DHT sensor. The output of the system is controlled, allowing precise control over devices.

This project demonstrates seamless integration of wireless communication (Bluetooth), environmental sensing (DHT), and home automation (Relay and PWM), offering a flexible and scalable solution for smart home applications.
<br>

  ### Working
  BlueSense Automation System is an advanced home automation solution designed to control AC-powered appliances such as bulbs, fans, and more, via Bluetooth connectivity. This system allows users to conveniently switch appliances on or off using their mobile phone. Additionally, the BlueSense Automation System integrates a DHT sensor, which continuously measures the room's temperature. Based on the temperature readings, the system can adjust the fan speed—either slowing it down or increasing it—to maintain a comfortable environment. This combination of Bluetooth control and environmental monitoring makes BlueSense an intelligent and efficient solution for modern smart homes.

  ### Components Required
  <ul>
  <li>RISC-V SoC Chip (e.g., CH32V00x series)</li>
  <li>Bluetooth Module (e.g., HC-05 or HC-06)</li>
  <li>DHT22 Sensor (for temperature and humidity readings)</li>
  <li>Relay Module (for switching devices)</li>
  <li>Power Supply (5V or 3.3V depending on the SoC and modules)</li>
  <li>Jumper Wires</li>
</ul>
<br>

  ### Pinout Diagram
  
  ![](https://github.com/amanbangeraa/samsung-riscv/blob/main/Task05/aman.jpg)
  
  <br>
  
  ### Pin Detais
 <table border="1" style="border-collapse: collapse; width: 100%;">
    <thead>
        <tr style="background-color: #f2f2f2;">
            <th>Component</th>
            <th>Pin</th>
            <th>Microcontroller GPIO</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>DHT22 Sensor</td>
            <td>VCC</td>
            <td>5V</td>
        </tr>
        <tr>
            <td></td>
            <td>GND</td>
            <td>GND</td>
        </tr>
        <tr>
            <td></td>
            <td>Data</td>
            <td>PC0</td>
        </tr>
        <tr>
            <td>HC05 Bluetooth Module</td>
            <td>VCC</td>
            <td>5V</td>
        </tr>
        <tr>
            <td></td>
            <td>GND</td>
            <td>GND</td>
        </tr>
        <tr>
            <td></td>
            <td>TX</td>
            <td>PD0 (RXD)</td>
        </tr>
        <tr>
            <td></td>
            <td>RX</td>
            <td>PD1 (TXD)</td>
        </tr>
        <tr>
            <td>Relay Module 1</td>
            <td>VCC</td>
            <td>5V</td>
        </tr>
        <tr>
            <td></td>
            <td>GND</td>
            <td>GND</td>
        </tr>
        <tr>
            <td></td>
            <td>Control</td>
            <td>PC4</td>
        </tr>
        <tr>
            <td>Relay Module 2</td>
            <td>VCC</td>
            <td>5V</td>
        </tr>
        <tr>
            <td></td>
            <td>GND</td>
            <td>GND</td>
        </tr>
        <tr>
            <td></td>
            <td>Control</td>
            <td>PC5</td>
        </tr>
    </tbody>
</table>

    

</details>
