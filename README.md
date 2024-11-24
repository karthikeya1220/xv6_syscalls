## Question 1:  System Calls Implemented: `cps`, `signal`, `pthread`, `message queue`

### Problem Overview
In this project we aimed to implement 4 new system calls and addd them to the xv6-riscv operating system.
#### 1. **cps**
   Displays all the processes currently running, their process IDs and current states.

#### 2. **pthread**
  Implemented a create thread function and alloted a kernel stack for each thread during execution.

#### 3. **signal**
   Implemented default handler for a user generated inteerupt (`SIG_INT`).<br/>
   Added Ctrl+C as a command to send a user-interrupt

.

### Methodology:
#### 1. **System Call Numbers**:
   Each system call has a unique number by which it it identified in the system call registry.<br/>
   Every time a system call is used, the system triggers an interrupt with a particular number which denotes the system call.
#### 2. **Definitions**:
   Implementation of the logic of the system call is divided among files to handle all the cases efficiently.
#### 3. **User-Space Wrapping**:
   The definitions and logic of the implementation of the system calls should not be accessible to the user.<br/>
   So, a wrapper function was inplemented in the user-space to send the arguments required by a system call which can be accessed from the user-space<br/>
   This wrapper function is responsible to pass all the required arguments to the system call.<br/>
   Important to add this wrapper function to the function registry to make sure that the function is mapped from the user-space to the kernel-space.

```
make clean
```
```
make
```
```
make qemu
```
#### For cps:
```
$ cps
```

#### For Thread:
```
$ thread_test
```

#### For Signal:
```
$ signal
```
---





