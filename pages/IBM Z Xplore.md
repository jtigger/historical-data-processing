- Setup
	- running OS/390 on a z14
		- a little C program I wrote to get this data:
		  collapsed:: true
			- ```C
			  #define _POSIX_SOURCE
			  #include <stdio.h>
			  #include <stdlib.h>
			  #include <sys/utsname.h>
			  
			  int main() {
			    struct utsname sysinfo;
			    int result = 0;
			  
			    printf("info -- z/OS system information\n\n");
			  
			    result = uname(&sysinfo);
			    if (result != 0) {
			      printf("\nError: __osname() failed with %d.\n", result);
			      return result;
			    }
			  
			    printf("Fetched system information:\n");
			    printf("- OS: %s\n", sysinfo.sysname);
			    printf("- node name: %s\n", sysinfo.nodename);
			    printf("- release: %s\n", sysinfo.release);
			    printf("- version: %s\n", sysinfo.version);
			    printf("- hardware: %s\n", sysinfo.machine);
			  
			    printf("\n");
			    return 0;
			  }
			  ```
		- it's output:
		  collapsed:: true
			- ```
			  info -- z/OS system information
			  
			  Fetched system information:
			  - OS: OS/390
			  - node name: S0W1
			  - release: 27.00
			  - version: 04
			  - hardware: 3906
			  ```
	- https://www.ibm.com/common/ssi/ShowDoc.wss?docURL=/common/ssi/rep_sm/1/897/ENUS3906-_h01/index.html
	- https://www-40.ibm.com/servers/resourcelink/lib03060.nsf/pages/z14
	-
	-
- Things I learned
	- [[The IEB Module Library]]
	- [[Unix System Services]]
	- [[z/OSMF]]
		-