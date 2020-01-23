
## Program for IPC - SharedMemory

# 1. Interprocess communication with shared memory

Client


[![code](https://img.shields.io/badge/-code-green.svg?logo=appveyor&longCache=true&style=for-the-badge)](https://github.com/Ajil5467/Network-Programming-Lab-/blob/master/InterProcessCommunication/SharedMemory/client.c.txt)

Server


[![code](https://img.shields.io/badge/-code-green.svg?logo=appveyor&longCache=true&style=for-the-badge)](https://github.com/Ajil5467/Network-Programming-Lab-/blob/master/InterProcessCommunication/SharedMemory/server.c.txt)


## Theory

**ftok()**: is use to generate a unique key.

**shmget()**: int shmget(key_t,size_tsize,intshmflg); upon successful completion, shmget() returns an identifier for the shared memory segment.

**shmat()**: Before you can use a shared memory segment, you have to attach yourself
to it using shmat(). void *shmat(int shmid ,void *shmaddr ,int shmflg);
shmid is shared memory id. shmaddr specifies specific address to use but we should set
it to zero and OS will automatically choose the address.

**shmdt()**: When you’re done with the shared memory segment, your program should
detach itself from it using shmdt(). int shmdt(void \*shmaddr);

**shmctl()**: when you detach from shared memory,it is not destroyed. So, to destroy
shmctl() is used. shmctl(int shmid,IPC_RMID,NULL);
