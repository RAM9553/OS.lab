 Write programs using the following UNIX operating system calls fork, exec, getpid, exit, wait, close, stat, opendir and readdir  

#include<stdio.h> 

int main()  

{  

int i; 

    for( i=0;i<5;i++)  

    {  

        if(fork() == 0)  

        {  

            printf("[son] pid %d from [parent] pid %d\n", getpid(), getppid());  

            exit(0);  

        }  

    }  

    for(i=0;i<5;i++)  

    wait(NULL);  

       

}  Program using opendir and readdir: 

 

#include <stdio.h> 

#include <dirent.h> 

 

int main() { 

    DIR *dir = opendir("."); 

if (dir == NULL) { 

perror("opendir failed"); 

return 1; 

    } 

 

structdirent *entry; 

printf("Contents of the current directory:\n"); 

while ((entry = readdir(dir)) != NULL) { 

printf("%s\n", entry->d_name); 

    } 

 

closedir(dir); 

return 0; 

} 
