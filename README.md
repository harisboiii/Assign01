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

Step 7: 

