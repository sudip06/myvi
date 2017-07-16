===========
Convenient search using bash
===========

myvi is a shell script to search and open files using vim at convenience.
One of the use is in the Linux kernel where one may search Makefiles and 
hundreds come up, using myvi helps the user in selecting the appropriate 
file.

In search results, it outputs the results segregating the files and directories 
easier fo the user to make a choice and open the selected file by his choice.

Also, it allows the user to choose the initial directory to start the search 
operation.

The script is run by bash shell.

Usage: myvi [-i] [-d initDir] <fileToSearch>
             -i: case incensitive search
             -d: initial directory to search

Testing
===========

Schenario 1:
===========
General Usage:

linux-headers-4.8.0-36-generic$ myvi -d . "Makefile"                   

(0)./arch/x86/entry/Makefile(f)
(1)./arch/x86/entry/syscalls/Makefile(f)
(2)./arch/x86/purgatory/Makefile(f)
(3)./arch/x86/Makefile(f)
(4)./arch/x86/kernel/Makefile(f)
(5)./arch/x86/tools/Makefile(f)
(6)./Makefile(f)
(7)./kernel/Makefile(f)
(8)./scripts/basic/Makefile(f)
(9)./scripts/mod/Makefile(f)
(10)./scripts/Makefile(f)
(11)./scripts/kconfig/Makefile(f)
(12)./scripts/selinux/genheaders/Makefile(f)
(13)./scripts/selinux/Makefile(f)
(14)./scripts/selinux/mdp/Makefile(f)
(15)./scripts/genksyms/Makefile(f)

Enter your choice:


Schenario 2: usage of initial directory for search
===========
rc$ myvi -d /usr/src/linux-headers-4.8.0-36-generic/ 8250*
(0)/usr/src/linux-headers-4.8.0-36-generic/include/config/serial/8250(d)
(1)/usr/src/linux-headers-4.8.0-36-generic/include/config/serial/8250.h(f)

Enter your choice:


Schenario 3: case incensitive
===========
rc$ myvi -i -d /usr/src/linux-headers-4.8.0-36-generic/ makefile      
(0)/usr/src/linux-headers-4.8.0-36-generic/arch/x86/entry/Makefile(f)
(1)/usr/src/linux-headers-4.8.0-36-generic/arch/x86/entry/syscalls/Makefile(f)
(2)/usr/src/linux-headers-4.8.0-36-generic/arch/x86/purgatory/Makefile(f)
(3)/usr/src/linux-headers-4.8.0-36-generic/arch/x86/Makefile(f)
(4)/usr/src/linux-headers-4.8.0-36-generic/arch/x86/kernel/Makefile(f)
(5)/usr/src/linux-headers-4.8.0-36-generic/arch/x86/tools/Makefile(f)
(6)/usr/src/linux-headers-4.8.0-36-generic/Makefile(f)
(7)/usr/src/linux-headers-4.8.0-36-generic/kernel/Makefile(f)
(8)/usr/src/linux-headers-4.8.0-36-generic/scripts/basic/Makefile(f)
(9)/usr/src/linux-headers-4.8.0-36-generic/scripts/mod/Makefile(f)
(10)/usr/src/linux-headers-4.8.0-36-generic/scripts/Makefile(f)
(11)/usr/src/linux-headers-4.8.0-36-generic/scripts/kconfig/Makefile(f)
(12)/usr/src/linux-headers-4.8.0-36-generic/scripts/selinux/genheaders/Makefile(f)
(13)/usr/src/linux-headers-4.8.0-36-generic/scripts/selinux/Makefile(f)
(14)/usr/src/linux-headers-4.8.0-36-generic/scripts/selinux/mdp/Makefile(f)
(15)/usr/src/linux-headers-4.8.0-36-generic/scripts/genksyms/Makefile(f)

Enter your choice:   




Authors
  - Sudip Midya
