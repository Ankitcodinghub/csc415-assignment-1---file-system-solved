# csc415-assignment-1---file-system-solved
**TO GET THIS SOLUTION VISIT:** [CSC415 Assignment 1 – File System Solved](https://www.ankitcodinghub.com/product/csc415-assignment-1-file-system-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;93541&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CSC415&nbsp;Assignment 1 - File System Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
&nbsp;

Over the past month you and your team have been designing components of a file system. You have defined the goals and designed the directory entry structure, the volume structure and the free space. Now it is time to implement your file system.

To help I have written the low level LBA based read and write. The routines are in fsLow.o, the necessary header for you to include file is fsLow.h. You do NOT need to understand the code in fsLow, but you do need to understand the header file and the functions. There are 2 key functions:

&nbsp;

`uint64_t LBAwrite (void * buffer, uint64_t lbaCount, uint64_t lbaPosition);`

`uint64_t LBAread (void * buffer, uint64_t lbaCount, uint64_t lbaPosition);`

LBAread and LBAwrite take a buffer, a count of LBA blocks and the starting LBA block number (0 based). The buffer must be large enough for the number of blocks * the block size.

On return, these function returns the number of **blocks** read or written.

&nbsp;

In addition, I have written a hexdump utility that will allow you to analyze your volume file in the Hexdump subdirectory.

**Your assignment is to write a file system!**

You will need to format your volume, create and maintain a free space management system, initialize a root directory and maintain directory information, create, read, write, and delete files, and display info. See below for specifics.

I will provide an initial “main” (fsShell.c) that will be the driver to test you file system. Your group can modifiy this driver as needed. The driver will be interactive (with all built in commands) to list directories, create directories, add and remove files, copy files, move files, and two “special commands” one to copy from the normal filesystem to your filesystem and the other from your filesystem to the normal filesystem.

You should modify this driver as needed for your filesystem, adding the display/setting of any additional meta data, and other functions you want to add.

The shell also calls two function in the file fsInit.c `initFileSystem` and `exitFileSystem` which are routines for you to fill in with whatever initialization and exit code you need for your file system.

Some specifics – you need to provide the following interfaces:

“`

b_io_fd b_open (char * filename, int flags);

int b_read (b_io_fd fd, char * buffer, int count);

int b_write (b_io_fd fd, char * buffer, int count);

int b_seek (b_io_fd fd, off_t offset, int whence);

void b_close (b_io_fd fd);

“`

Note that the function are similar to the b_read and b_write you have done, there is a signifigant difference since you do not have the linux open and read to use.

You have to have methods of locating files, and knowing which logical block addresses are associated with the file.

Directory Functions – see [https://www.thegeekstuff.com/2012/06/c-directory/](https://www.thegeekstuff.com/2012/06/c-directory/) for reference.

“`

int fs_mkdir(const char *pathname, mode_t mode);

int fs_rmdir(const char *pathname);

fdDir * fs_opendir(const char *name);

struct fs_diriteminfo *fs_readdir(fdDir *dirp);

int fs_closedir(fdDir *dirp);

char * fs_getcwd(char *buf, size_t size);

int fs_setcwd(char *buf); //linux chdir

int fs_isFile(char * path); //return 1 if file, 0 otherwise

int fs_isDir(char * path); //return 1 if directory, 0 otherwise

int fs_delete(char* filename); //removes a file

struct fs_diriteminfo

{

unsigned short d_reclen; /* length of this record */

unsigned char fileType;

char d_name[256]; /* filename max filename is 255 characters */

};

“`

Finally file stats – not all the fields in the structure are needed for this assingment

“`

int fs_stat(const char *path, struct fs_stat *buf);

struct fs_stat

{

off_t st_size; /* total size, in bytes */

blksize_t st_blksize; /* blocksize for file system I/O */

blkcnt_t st_blocks; /* number of 512B blocks allocated */

time_t st_accesstime; /* time of last access */

time_t st_modtime; /* time of last modification */

time_t st_createtime; /* time of last status change */

/* add additional attributes here for your file system */

};

“`

These interfaces will also be provided to you in mfs.h.

**Note:** You will need to modify mfs.h for the fdDIR strucutre to be what your file system need to maintain and track interation through the directory structure.

A shell program designed to demonstrate your file system called fsshell.c is proviced. It has a number of built in functions that will work if you implement the above interfaces, these are:

“`

ls – Lists the file in a directory

cp – Copies a file – source [dest]

mv – Moves a file – source dest

md – Make a new directory

rm – Removes a file or directory

cp2l – Copies a file from the test file system to the linux file system

cp2fs – Copies a file from the Linux file system to the test file system

cd – Changes directory

pwd – Prints the working directory

history – Prints out the history

help – Prints out help

“`

This is deliberately vague, as it is dependent on your filesystem design. And this all you may get initially for a real-world assignment, so if you have questions, please ask.

We will discuss some of this in class.

For our purposes use 10,000,000 or less (minimum 500,000) bytes for the volume size and 512 bytes per sector. These are the values to pass into startPartitionSystem.

What needs to be submitted (via GitHub and iLearn):

* All source files (.c and .h)

* Modified Driver program (must be a program that just utilizes the header file for your file system).

* The Driver program must be named: `fsshell.c`

* A make file (named “Makefile”) to build your entire program

* A PDF writeup on project that should include (this is also submitted in iLearn):

* The github link for your group submission.

* A description of your file system

* Issues you had

* Detail of how your driver program works

* Screen shots showing each of the commands listed above

* Your volume file (limit 10MB)

* There will also be an INDIVIDUAL report (form) to complete.

&nbsp;
