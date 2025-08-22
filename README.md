🎯 vnethOperating

MyOS: A Simple x86 Operating System Kernel
    Welcome to MyOS!

MyOS is an educational, minimalist operating system kernel built for x86 architecture, combining low-level Assembly boot code with a higher-level C kernel. This project provides a hands-on journey into the fundamentals of OS development, from the initial boot sector to basic kernel initialization.

✨ Features

    1.Dual-Language Foundation:

    2.Assembly Bootloader: A custom 16-bit real mode boot sector written in NASM that handoffs control to the kernel.

    3.C Kernel: The core kernel logic written in C, demonstrating the transition to a higher-level language after boot.

    4.Basic Boot Process:

          Successfully initializes and displays a boot message via the BIOS.
  
          Prepares the system for loading the kernel into memory.

    5.Cross-Platform Development:

         Built using standard tools (NASM, GCC, LD) within a Linux/WSL2 environment.
 
         Tested using the QEMU system emulator for safe and efficient development.

🛠️ Built With

    1.NASM (Netwide Assembler): For assembling the x86 boot sector code (boot.asm).

    2.GCC Cross-Compiler: Used with -m32 and -ffreestanding flags to compile the 32-bit C kernel (kernel.c).

    3.GNU LD (Linker): For linking the kernel object file into a final binary using a custom linker script (linker.ld).

    4.QEMU: The primary emulator for testing the OS without needing physical hardware.

🎯 Inspiration & Acknowledgments

This project is inspired by the countless educational OS development tutorials and resources available online. It serves as a practical implementation of the core concepts behind booting and kernel initialization, paying homage to the great learning materials provided by the OSDev community.

💻 Getting Started

To build and run MyOS:

    1.Prerequisites: Ensure you have nasm, gcc, ld, and qemu-system-x86_64 installed.

    2.Assemble the Bootloader:

        nasm -f bin boot.asm -o boot.bin

    3.Compile and Link the Kernel:

        gcc -m32 -ffreestanding -c kernel.c -o kernel.o
        ld -m elf_i386 -T linker.ld -o kernel.bin kernel.o
        
    4.Create a Full Disk Image (combining boot and kernel) and run it in QEMU.

📸 Development Snapshots

1. Successful Boot Sector Execution:

    <img width="726" height="464" alt="Screenshot 2025-06-25 094955" src="https://github.com/user-attachments/assets/8b64555e-327b-4b63-911b-30df52b9c7e9" />

The bootloader successfully loads and begins execution, displaying a simple message as Hi.

2. Active Development Environment:

    <img width="1399" height="376" alt="Screenshot 2025-06-25 095537" src="https://github.com/user-attachments/assets/70067e32-e69e-4537-8752-3619111ed5c2" />

The core development workflow, showing the compilation and linking process in a WSL2 terminal.

3. Toolchain in Action:

    <img width="1406" height="377" alt="Screenshot 2025-06-25 095603" src="https://github.com/user-attachments/assets/59eb0719-df44-4410-a32e-11c571e4d82e" />

A close look at the commands and compiler warnings during the build process, a common sight in OS development.
