#  Learning Python(5th edition)

## 1. Preface
Python is a multi-paradigm language

## A Python Q&A Session
### Why Do People Use Python?
*  Software quality: readable, reuseable
*  Developer productivity: no need to compile, 1/3 or 1/4 size of C++ or Java code
*  Program portability: Windows/Linux/Mac OS
*  Support libraries: so much libraries
*  Component integration: can call C libraries, Java or .Net compoenets
*  Enjoyment

##  2. How Python Runs Programs
### Python Interpreter
read program and carries out the instructions. between python code and hardware, an interpreter can be a native program(C program) or java set
### byte code
"textcode.py" --(compile)-> "bytecode.pyc"(lower-level, platform-independent ) ->
In 3.2 and later, bytecode saved in "\__pycache__" subdirectory.
Only imported files save to bytecode file
### The Python Virtual Machine(PVM)
used to run byte code

## 3.  How You Run Programs
### Module Imports and Reloads
* Every file of Python source code with .py extension is a module.
* Other file ca access the items a module defines by importing the module
```python
    #import a module, only work for first time import
    import a_python_module #this line works
    import a_python_module #this line does not work
```
* reload a module
```python
    #reload a module
    from imp import reload
    import a_python_module #must import a module first, then you can reload it
    reload(a_python_module) #this line works
    reload(a_python_module) #this line works too
```
* you can access the variables, functions, class in a module by 2 methods
1. attribute
```python
    #access a variables by attribute
    import a_python_module
    a_python_module.variables_in_module #use . to qualify a attribute
```
2. "from" statement
```python
    #access a variables by 'from' statement
    from a_python_module import variables_in_module
    variables_in_module #do not need use . to qualify
```
use 'dir' to get all attribute of a module
```python
    >>> import os
    >>> dir(os)  #take os as an example
    ['CLD_CONTINUED', 'CLD_DUMPED', 'CLD_EXITED', 'CLD_TRAPPED', 'EX_CANTCREAT', 'EX_CONFIG', 'EX_DATAERR', 'EX_IOERR', 'EX_NOHOST', 'EX_NOINPUT', 'EX_NOPERM', 'EX_NOUSER', 'EX_OK', 'EX_OSERR', 'EX_OSFILE', 'EX_PROTOCOL', 'EX_SOFTWARE', 'EX_TEMPFAIL', 'EX_UNAVAILABLE', 'EX_USAGE', 'F_LOCK', 'F_OK', 'F_TEST', 'F_TLOCK', 'F_ULOCK', 'MutableMapping', 'NGROUPS_MAX', 'O_ACCMODE', 'O_APPEND', 'O_ASYNC', 'O_CLOEXEC', 'O_CREAT', 'O_DIRECT', 'O_DIRECTORY', 'O_DSYNC', 'O_EXCL', 'O_LARGEFILE', 'O_NDELAY', 'O_NOATIME', 'O_NOCTTY', 'O_NOFOLLOW', 'O_NONBLOCK', 'O_PATH', 'O_RDONLY', 'O_RDWR', 'O_RSYNC', 'O_SYNC', 'O_TMPFILE', 'O_TRUNC', 'O_WRONLY', 'POSIX_FADV_DONTNEED', 'POSIX_FADV_NOREUSE', 'POSIX_FADV_NORMAL', 'POSIX_FADV_RANDOM', 'POSIX_FADV_SEQUENTIAL', 'POSIX_FADV_WILLNEED', 'PRIO_PGRP', 'PRIO_PROCESS', 'PRIO_USER', 'P_ALL', 'P_NOWAIT', 'P_NOWAITO', 'P_PGID', 'P_PID', 'P_WAIT', 'RTLD_DEEPBIND', 'RTLD_GLOBAL', 'RTLD_LAZY', 'RTLD_LOCAL', 'RTLD_NODELETE', 'RTLD_NOLOAD', 'RTLD_NOW', 'R_OK', 'SCHED_BATCH', 'SCHED_FIFO', 'SCHED_IDLE', 'SCHED_OTHER', 'SCHED_RESET_ON_FORK', 'SCHED_RR', 'SEEK_CUR', 'SEEK_DATA', 'SEEK_END', 'SEEK_HOLE', 'SEEK_SET', 'ST_APPEND', 'ST_MANDLOCK', 'ST_NOATIME', 'ST_NODEV', 'ST_NODIRATIME', 'ST_NOEXEC', 'ST_NOSUID', 'ST_RDONLY', 'ST_RELATIME', 'ST_SYNCHRONOUS', 'ST_WRITE', 'TMP_MAX', 'WCONTINUED', 'WCOREDUMP', 'WEXITED', 'WEXITSTATUS', 'WIFCONTINUED', 'WIFEXITED', 'WIFSIGNALED', 'WIFSTOPPED', 'WNOHANG', 'WNOWAIT', 'WSTOPPED', 'WSTOPSIG', 'WTERMSIG', 'WUNTRACED', 'W_OK', 'XATTR_CREATE', 'XATTR_REPLACE', 'XATTR_SIZE_MAX', 'X_OK', '_DummyDirEntry', '_Environ', '__all__', '__builtins__', '__cached__', '__doc__', '__file__', '__loader__', '__name__', '__package__', '__spec__', '_dummy_scandir', '_execvpe', '_exists', '_exit', '_fwalk', '_get_exports_list', '_putenv', '_spawnvef', '_unsetenv', '_wrap_close', 'abort', 'access', 'altsep', 'chdir', 'chmod', 'chown', 'chroot', 'close', 'closerange', 'confstr', 'confstr_names', 'cpu_count', 'ctermid', 'curdir', 'defpath', 'device_encoding', 'devnull', 'dup', 'dup2', 'environ', 'environb', 'errno', 'error', 'execl', 'execle', 'execlp', 'execlpe', 'execv', 'execve', 'execvp', 'execvpe', 'extsep', 'fchdir', 'fchmod', 'fchown', 'fdatasync', 'fdopen', 'fork', 'forkpty', 'fpathconf', 'fsdecode', 'fsencode', 'fstat', 'fstatvfs', 'fsync', 'ftruncate', 'fwalk', 'get_blocking', 'get_exec_path', 'get_inheritable', 'get_terminal_size', 'getcwd', 'getcwdb', 'getegid', 'getenv', 'getenvb', 'geteuid', 'getgid', 'getgrouplist', 'getgroups', 'getloadavg', 'getlogin', 'getpgid', 'getpgrp', 'getpid', 'getppid', 'getpriority', 'getresgid', 'getresuid', 'getsid', 'getuid', 'getxattr', 'initgroups', 'isatty', 'kill', 'killpg', 'lchown', 'linesep', 'link', 'listdir', 'listxattr', 'lockf', 'lseek', 'lstat', 'major', 'makedev', 'makedirs', 'minor', 'mkdir', 'mkfifo', 'mknod', 'name', 'nice', 'open', 'openpty', 'pardir', 'path', 'pathconf', 'pathconf_names', 'pathsep', 'pipe', 'pipe2', 'popen', 'posix_fadvise', 'posix_fallocate', 'pread', 'putenv', 'pwrite', 'read', 'readlink', 'readv', 'remove', 'removedirs', 'removexattr', 'rename', 'renames', 'replace', 'rmdir', 'scandir', 'sched_get_priority_max', 'sched_get_priority_min', 'sched_getaffinity', 'sched_getparam', 'sched_getscheduler', 'sched_param', 'sched_rr_get_interval', 'sched_setaffinity', 'sched_setparam', 'sched_setscheduler', 'sched_yield', 'sendfile', 'sep', 'set_blocking', 'set_inheritable', 'setegid', 'seteuid', 'setgid', 'setgroups', 'setpgid', 'setpgrp', 'setpriority', 'setregid', 'setresgid', 'setresuid', 'setreuid', 'setsid', 'setuid', 'setxattr', 'spawnl', 'spawnle', 'spawnlp', 'spawnlpe', 'spawnv', 'spawnve', 'spawnvp', 'spawnvpe', 'st', 'stat', 'stat_float_times', 'stat_result', 'statvfs', 'statvfs_result', 'strerror', 'supports_bytes_environ', 'supports_dir_fd', 'supports_effective_ids', 'supports_fd', 'supports_follow_symlinks', 'symlink', 'sync', 'sys', 'sysconf', 'sysconf_names', 'system', 'tcgetpgrp', 'tcsetpgrp', 'terminal_size', 'times', 'times_result', 'truncate', 'ttyname', 'umask', 'uname', 'uname_result', 'unlink', 'unsetenv', 'urandom', 'utime', 'wait', 'wait3', 'wait4', 'waitid', 'waitid_result', 'waitpid', 'walk', 'write', 'writev']
```

## 4.Introducing Python Object Types
**In Python, data takes the form of objects.**
### The Python Conceptual Hierarchy
1. Programs are composed of modules
2. Modules contain statements
3. Statements contain expressions
4. Expressions create and process objects
### Built-in objects
| Object type        | Example  |immutable|
| ------------- |:-------------:|:-------------:|
| Numbers      | 1234 , 3.1415 , 3+4j , 0b111 , Decimal() , Fraction()  |yes|
| String      | 'spam' , "Bob's" , b'a\x01c' , u'sp\xc4m'       |yes|
| Lists | [1, [2, 'three'], 4.5] , list(range(10))       |no|
|Dictionaries||no|
{'food': 'spam', 'taste': 'yum'} , dict(hours=10) |
|Tuples|(1, 'spam', 4, 'U') , tuple('spam') , namedtuple |yes|
|Files|open('eggs.txt') , open(r'C:\ham.bin', 'wb') |
|Sets|set('abc') , {'a', 'b', 'c'} |no|
|Other core types|Booleans, types, None |
|Program unit types||
|Implementation-related types||

### 1. Numbers
Numbers: integers,float
``` python
>>> a = 6
>>> b = 4
>>> a + b
10
>>> a - b
2
>>> a * b
24
>>> a / b
1.5
>>> a % b
2
>>> a ** b
1296
#get length of a number
>>> len(str(a ** b))
4
#another way to get the length of a number
>>> import math
>>> math.ceil(math.log(a ** b, 10))   
4
#by the way, to get down round use floor
>>> math.floor(math.log(a ** b, 10))   
3
#random number
>>> import random
>>> random.random()
0.4298670529747527
>>> random.random()
0.16527417288683433
>>> random.random()
0.9306263521427348
>>> random.choice([1,2,3,4])
2
>>> random.choice([1,2,3,4])
3
>>> random.choice([1,2,3,4])
1
```
### 2. Strings
* String is a sequence of a character
```python
#define a String
>>> S = 'Spam'
>>> len(S)
4
#index of String
>>> S[0]
'S'
>>> S[1]
'p'
>>> S[-1]
'm'
>>> S[-2]
'a'
#1 is start index, 3 is end index(not include in substring)
>>> S[1:3]
'pa'
>>> S[1:] 
'pam'
>>> S[:]
'Spam'
>>> S[0:4]
'Spam'
#concat String
>>> S+'xyz'
'Spamxyz'
#Repetition of String
>>> S * 8
'SpamSpamSpamSpamSpamSpamSpamSpam'
```
* Immutability: Strings can't be modified
```python
#S is a new String
>>> S+='xyz'
>>> S
'Spamxyz'
```
* String to List
```python
>>> L=list(S)
>>> L
['S', 'p', 'a', 'm', 'x', 'y', 'z']
```
* List to String
```python
>>> S2=''.join(L)
>>> S2
'Spamxyz'
```
* String vs bytes vs bytearray
String and bytes are immutable, bytearray is mutable
```python
# String to bytes
>>> B=S.encode()
>>> B
b'Spamxyz'
# bytes to String
>>> S2=B.decode()
>>> S2
'Spamxyz'
```
* Type-Specific Methods
```python
>>> S='Spam'
>>> S.find('pa')
1
#here, S is immutable, it create a new String
>>> S.replace('pa', 'XYZ')
'SXYZm'
>>> S
'Spam'
>>> line = 'aaa,bbb,ccccc,dd'
>>> line.split(',')
['aaa', 'bbb', 'ccccc', 'dd']
>>> S.upper()
'SPAM'
>>> S.isalpha()
True
#format string, 3.1+
>>> '{}, eggs, and {}'.format('spam', 'SPAM!')
'spam, eggs, and SPAM!'
```




