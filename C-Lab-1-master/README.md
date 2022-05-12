# Lab 0

##Learning Objectives:\*\*

- Set up your computing environment for the rest of the quarter.
- Compile and run C code on a Linux environment.
- Observe C programming behaviors that will preview the topics covered in the later labs.
- Fill out quiz on canvas

Be sure to read the [ ![](../images/icon_txt.png) Linux tips](../linux/) page to set up your environment and pick a text editor before starting this lab.  
Instructions on what to do are in the Cavas quiz along with comments in the starter code.

### 1 Github and SSH - first steps

Follow instructions here

[Github](https://www.cs.sfu.ca/~ashriram/Courses/CS295/labs/lab0.html)

#### Editing Code

After acquiring the source file, you will need to open `lab1.c` in your [emacs editor](https://www.cs.sfu.ca/~ashriram/Courses/CS295/assets/demos/cheats/cheat-editor.pdf) of choice. See the tutorials if you are unsure how to make edits.

\*\* If you are familiar

The `lab1.c` file contains a number of comments explaining some basics of C. There are five different parts to this lab and you will need to modify or write some lines of code for each one. We recommend keeping a fresh copy of `lab1.c` around for reference (as you may lose track of all the changes you end up making).
In particular, it will be helpful for this lab (and for using C moving forward) if you take a little time to familiarize yourself with [the printf() function](http://www.cplusplus.com/reference/cstdio/printf/), which is used to output formatted messages to the console.

#### Compiling Code

The source file `lab1.c` won't do anything by itself; you need a compiler (specifically the GNU C compiler) to generate to an executable from it. The GNU C compiler is available on the instructional Linux machines in the lab.

Using any one of these machines, open a terminal and execute `gcc -v`. We see:

```
$ gcc -v
Using built-in specs.
COLLECT\_GCC=gcc
COLLECT\_LTO\_WRAPPER=/opt/rh/devtoolset-7/root/usr/libexec/gcc/x86\_64-redhat-linux/7/lto-wrapper
Target: x86\_64-redhat-linux
Configured with: ../configure --enable-bootstrap --enable-languages=c,c++,fortran,lto --prefix=/opt/rh/devtoolset-7/root/usr --mandir=/opt/rh/devtoolset-7/root/usr/share/man --infodir=/opt/rh/devtoolset-7/root/usr/share/info --with-bugurl=http://bugzilla.redhat.com/bugzilla --enable-shared --enable-threads=posix --enable-checking=release --enable-multilib --with-system-zlib --enable-\_\_cxa\_atexit --disable-libunwind-exceptions --enable-gnu-unique-object --enable-linker-build-id --with-gcc-major-version-only --enable-plugin --with-linker-hash-style=gnu --enable-initfini-array --with-default-libstdcxx-abi=gcc4-compatible --with-isl=/builddir/build/BUILD/gcc-7.3.1-20180303/obj-x86\_64-redhat-linux/isl-install --enable-libmpx --enable-gnu-indirect-function --with-tune=generic --with-arch\_32=i686 --build=x86\_64-redhat-linux
Thread model: posix
gcc version 7.3.1 20180303 (Red Hat 7.3.1-5) (GCC)
```

The output tells me a bunch of the configuration options for the my installation of GCC as well as the version number, which is 7.3.1. Assuming that you have saved `lab1.c` somewhere on your machine, navigate to that directory and then use GCC to compile it with the following command:

```
$ gcc -g -Wall -std=c99 -o lab1.bin lab1.c
```

It's not that important right now for you to know what all of these options do, but `-g` tells the compiler to include debugging symbols, `-Wall` says to print warnings for all types of potential problems, `-std=c99` says to use the C99 standard (now only 19 years old!), `-o lab1` instructs the compiler to output the executable code to a file called `lab1`, and `lab1.c` is the source file being compiled.

During execution of that command, you can safely ignore warning about unused variables if you haven't made any changes yet. This warning would not be shown if you removed `-Wall` from the `gcc` command, but you will want `-Wall` to catch potential errors when you write code yourself.

Having executed the `gcc` command, you should be able to see a file named `lab1` in the same directory:

```
$ ls
lab1  lab1.c
```

#### Running Executables

The `lab1` file is an _executable file_, which you can run using the command `./lab1.bin`. You should see:

```
$ ./lab1.bin
Usage: ./lab1.bin <num>
```

In this case, the executable `lab1` is expecting a _command-line argument_, which is text that is provided to the executable from the command-line when the program is run. In particular, `lab1` wants a number from 1 to 5, corresponding to which part of the lab code you want to run. See `main()` in `lab1.c` for more details. For example (your values of `p` and `q` may differ):

```
$ ./lab1.bin 1
\*\*\* LAB 1 PART 1 \*\*\*
x = 295
y = 410
p = 0x7fffaec6a2ec
q = 0x7fffaec6a2e8
x & x = 295
```

#### Checking Your Work

With that, you should have everything you need to complete the assignment. Show your code to the TA; you will want to work on the different parts of the lab in order (from 1 to 5). Each question can be answered and/or verified by appropriate edits to the source code. Note that every time you want to test a code modification, you will need to use the `gcc -g -Wall -std=c99 -o lab1.bin lab1.c` command to produce an updated `lab1.bin` executable file (**Tip:** Use the up and down keys to scroll through previous terminal commands you've executed).

You can submit each question individually on the Lab 0 submission page in your report coursys.
Most of the code behaviors will seem inexplicable at this point, but our goal is that you will be able to explain to someone else what is going on by the end of this course! =)

## To submit

- Commit the code to your repository.
- Fill out Quiz Lab 1 in Canvas
