# Linux-kernel-Project
This is Project1 for Linux Kernel

這是Linux kernel 的 Project 1  
Description :  
  
Add a new system call void linux_survey_TT(int, char *) to your Linux kernel so that you can call it in your program. The system call has the following properties.

    The system call has a parameter which specifies the PID of the process that you want to observe.
    The system call has another parameter which specifies the address of a memory area that can store all information the system call collects in the kernel. You may need to design the layout of the memory area to store your information.
    The system call records the virtual address intervals consisting of the user address space of the process specified by the parameter.
    The system call records the corresponding physical address intervals used by the above virtual address intervals at the moment that you execute system call void linux_survey_TT(). 

Execute a firefox browser on your Linux host with a 32-bit architecture. You can use command ps to obtain the PID of this process.
The process executing the above firefox program is called process 1 hereafter.
After obtaining the PID of the above firefox browser, open six other firefox browsers and let every of these six firefox browsers plays a video using Youtube.
During your experiments, do not terminate any of the above firefox browsers.
Write a program test.c as follows to collect the information you need. Execute this program after your start all required programs.


                #include <stdio.h>
                #include <unistd.h>
                #define  REPEAT_TIME      10
                #define  MEMORY_SIZE      10000 

                main()
                { int    i,pid; 
                  char   rslt[MEMORY_SIZE];
                     :   // Definition of other varialbes you need to use in your program
       
                     :   // Your initialization code
                  printf("Input the PID of the process that you want to observe:");
                  scanf("%d", &pid);
                  for(i=0;i<REPEAT_TIME;i++)
                  {
                    linux_survey_TT(pid,result);

                             :  // Code to process results contained in rslt[5000] 

                    sleep(120);
                  }
                    :  // Code to report the final results
                }                 
               

List the virtual address intervals consisting of the user address space of process 1.  

For each call to system call void linux_survey_TT(), list the corresponding physical address intervals used by the above virtual address intervals at the moment that you execute system call void linux_survey_TT(). And based on the result, show the percentage of virtual addresses that have physical memory assigned to them.  

List the total amount of main memory of your host.   


Execute another new firefox browser on your host, while the above seven brwosers, including process 1, are still executed.  
The process executing the above new firefox program is called process 2 hereafter.  
List the virtual address intervals consisting of the user address space of process 2.  
List the corresponding physical address intervals used by the above virtual address intervals at the moment that you execute system call void linux_survey_TT().  
List the virtual address intervals of process 1 that overlaps the virtual address intervals of process 2.  
List the physical address intervals of process 1 that overlaps the physical address intervals of process 2.   
