# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
# Ex02-OS-Linux-Process API - fork(), wait(), exec()
Operating systems Lab exercise


# AIM:
To write C Program that uses Linux Process API - fork(), wait(), exec()

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - fork(), wait(), exec()

### Step 3:

Test the C Program for the desired output. 

# PROGRAM:

## C Program to print process ID and parent Process ID using Linux API system calls
```
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>
int main(void)
{	//variable to store calling function's process id
	pid_t process_id;
	//variable to store parent function's process id
	pid_t p_process_id;
	//getpid() - will return process id of calling function
	process_id = getpid();
	//getppid() - will return process id of parent function
	p_process_id = getppid();
	//printing the process ids

//printing the process ids
	printf("The process id: %d\n",process_id);
	printf("The process id of parent function: %d\n",p_process_id);
	return 0; }


```
## OUTPUT
![output1](https://github.com/user-attachments/assets/46e52070-e7c3-454c-b11d-7c795a66256a)











## C Program to create new process using Linux API system calls fork() and exit()

```
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>
#include<stdlib.h>
int main()
{ int pid; 
pid=fork(); 
if(pid == 0) 
{ printf("Iam child my pid is %d\n",getpid()); 
printf("My parent pid is:%d\n",getppid()); 
exit(0); } 
else{ 
printf("I am parent, my pid is %d\n",getpid()); 
sleep(100); 
exit(0);} 
}
```











## OUTPUT

![output1](https://github.com/user-attachments/assets/3047e012-f4f4-4e2e-9394-d22552a6ffff)






## C Program to execute Linux system commands using Linux API system calls exec() family

```

#include <stdio.h>
#include <unistd.h>
#include <stdlib.h>
#include <sys/wait.h>
#include <sys/types.h>
int main()
{       int status;
        printf("Running ps with execlp\n");
        execl("ps", "ps", "ax", NULL);
        wait(&status);
        if (WIFEXITED(status))
                printf("child exited with status of %d\n", WEXITSTATUS(status));
        else
                puts("child did not exit successfully\n");
        printf("Done.\n");
printf("Running ps with execlp. Now with path specified\n");
        execl("/bin/ps", "ps", "ax", NULL);
        wait(&status);
        if (WIFEXITED(status))
                printf("child exited with status of %d\n", WEXITSTATUS(status));
        else
                puts("child did not exit successfully\n");
        printf("Done.\n");
        exit(0);}//C Program to execute Linux system commands using Linux API system calls exec() family



```

## OUTPUT

![otuputcc_3](https://github.com/user-attachments/assets/40999526-3bc4-420b-a91a-3747791b7ab3)
![outputcc_4](https://github.com/user-attachments/assets/cd545bb0-4216-4a9b-9288-e48418f68505)
![outputcc_5](https://github.com/user-attachments/assets/3d76fc49-ab62-4ac7-8078-d3b7d4f7b839)
![outputcc_6](https://github.com/user-attachments/assets/ea77263d-30f8-4da6-a7f3-368dfde32bd6)
![outputcc_7](https://github.com/user-attachments/assets/224729d5-e841-40eb-a902-bf1219b05950)
![outputcc_8](https://github.com/user-attachments/assets/bf2301ed-aae9-4626-b44f-25e8c08d8097)

# RESULT:
The programs are executed successfully.
