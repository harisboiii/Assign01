# Assign01
OS Theory Assignment 1, K213061

# System Call Assignment

Step 1: First we will download Kernel from kernel.org i did 4.19.272 Version [tarball] format. After it is downloaded extract the folder and in the extracted folder will make a new folder named 'hello'. ![image](https://user-images.githubusercontent.com/125253097/219947742-03ece96f-6d9d-4480-a79d-8b41184e4938.png)

Step 2: In that folder, Run a terminal, we'll make two files 'hello.c' (our task to run) and Makefile via terminal commands 'gedit hello.c' and gedit Makefile respectively. ![image](https://user-images.githubusercontent.com/125253097/219947812-c9a88e6b-487c-42aa-850a-8f8b9878139b.png)

Step 3: In hello.c write this code 
        #include <linux/kernel.h>
        asmlinkage long sys_hello(void)
        {
             printk("Hello world\n");
             return 0;
        }
        
Step 4; In Makefile add this       
         obj-y := hello.o
         
Step 5: We have to add the system call entry into the syscall_64.tbl file which keeps the name of all the system. For doing this we will open that file by running command in terminal which will open a file like this, ![image](https://user-images.githubusercontent.com/125253097/219951085-1d7818db-4cc6-441d-a12f-24e402379bb2.png)

step 6: In the syscall_64.tbl file scroll down to line [334], in the next line put this line (which will be line 335), then save the file. ![image](https://user-images.githubusercontent.com/125253097/219951399-5acda64f-e18c-4b54-b378-a308e0c98e34.png)

Step 7: Now we have to add the prototype of our system call in the system’s header file. In kernel folder “/include/linux/syscalls.h” we have to add the prototype
of our system call function in this file. By running the gedit command a file will be opened as shown, ![image](https://user-images.githubusercontent.com/125253097/219951817-017f7a3e-9653-4733-9e01-404d0f77c489.png)

Step 8: In this file we just have to add our function call in the system file by simply typing in the function name in the end, save it. ![image](https://user-images.githubusercontent.com/125253097/219951989-8528cbc3-8746-46b3-9db9-454c2835877a.png)

Step 9: Open Makefile and in Extraversion put the value equal to the roll number as shown.![image](https://user-images.githubusercontent.com/125253097/219953544-1d02c109-433a-49a1-9ecf-db922d45d262.png)


Step 10: Press CTRL+F in the same file and search for "core-y", navigate to second instance and in the end of the line put " hello/" as shown ![image](https://user-images.githubusercontent.com/125253097/219953680-9822e250-5072-4d7c-a2e7-5211bdec526c.png)

Step 11: We have to create a config file for our kernel. First, we search for the current config, copy the config, typing “cp /boot/config-4.10.0-28-generic /workingdirectory” ![image](https://user-images.githubusercontent.com/125253097/219954387-67751917-f50f-4003-8951-f0610066c944.png)

Step 12: We will now write the configuration file ![image](https://user-images.githubusercontent.com/125253097/219956980-a2fd8c95-e69b-4dcb-8b68-c1737f0ca757.png)
Here we can see the config file is successfully created ![image](https://user-images.githubusercontent.com/125253097/219957031-81b0484a-ed40-478e-9f88-6de06c1a49b8.png)

Step 13: We have to clean our processes in the kernel by typing “make clean -j4” , we now type “make -j4” to start building our kernel ![image](https://user-images.githubusercontent.com/125253097/219957293-b167b573-510d-4688-87a6-5115b19a4146.png)

Step 14: 
