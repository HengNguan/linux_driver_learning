## At 0* folder, run below to make the target
- Requisite : *.c and Makefile exist 

  ~~~
  make
  ~~~

## Commands to manage the module

- Following the kernel's log for new lines
  ~~~
  sudo dmesg -W
  ~~~
- Inserting the module:
  ~~~
  sudo insmod hello.ko  // --> static int __init my_init
  ~~~
- Removing the module:
  ~~~
  sudo rmmod hello.ko  // --> static void __exit my_exit
  ~~~


## Commands for managing kernel modules

- Showing the Kernel module's metadata:
  ~~~
  # With path and filename
  modinfo ./hello.ko
  # For modules shipped with our kernel
  modinfo industrialio
  ~~~
- Listing all the loaded modules
  ~~~
  lsmod
  # Search for our one
  lsmod | grep hello
  ~~~
- Showing the Kernel's log
  ~~~
  # The whole kernel's log
  sudo dmesg
  # Just the last 5 lines of the log
  sudo dmesg | tail -n 5
  # Print out kernel's log and follow for new lines
  sudo dmesg -w
  ~~~
- Loading module with its dependencies (just for modules shipped with our installed kernel)
  ~~~
  sudo modprobe industrialio
  ~~~
- Removing the module:
  ~~~
  # with path and filename
  sudo rmmod ./hello.ko
  # with module's name as shown in lsmod
  sudo rmmod hello
  ~~~