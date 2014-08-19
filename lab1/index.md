#Lab 1 - Introduction to VirtualBox and Unix

VirtualBox is a free program that allows you to run another operating system on your machine without needing to reinstall anything. You just have to install the VirtualBox client, which installs like any other program and is available for many different platforms (Windows, Mac, Linux). Our lab computers have VirtualBox installed with a Ubuntu Linux virtual machine.

## [VirtualBox] (http://www.virtualbox.org)
###Quick start

* A bit of terminology: the 'host' machine is the physical computer (laptop, desktop, etc.) that you are using. The 'guest' machine is the virtual machine that is running in VirtualBox, and is often just called the 'guest operating system'.
* Run VirtualBox
* Boot the Ubuntu Linux machine (click the Start icon at the top - it's a green rightward pointing arrow). You may notice some display artifacts during boot-up as the virtual machine changes video modes, but that will stabilize once booting has completed.
* No login is required. 
  * The [documentation](http://www.virtualbox.org/manual/UserManual.html) is available online, although most of the salient details are listed on this page.

###Notes
* The 'host key' is defined by your host machine's operating system (it's the right control button under Linux, for example). This key is used for a number of contexts, including un-capturing the mouse. To have VirtualBox warn you about what the host key is, you can reset all warnings via the VirtualBox help menu, and it will warn you about this at boot-up.
* We did not install the latest version of Ubuntu, but instead installed the Long-Term Support (LTS) version, which is 14.04. The difference is that the LTS versions are supported for far longer (3 years or so) than the non-LTS versions (which are only supported for a year or so). 
* Sound and network should work automatically, as the VirtualBox program will connect those to your host machine's sound and network device drivers.

###How-Tos

* To load a terminal (a.k.a. command prompt): click the search button at the upper left corner, then search for Terminal.  You can also click on the command-prompt icon on the left toolbar to get a terminal window.
* To toggle between full-screen and windowed mode, click on the host key and 'f'. Don't know what the host key is? Read the bullet point about this in the 'Notes' section, above.
* To change the screen resolution: from the top menu bar, click on the circular power button icon on the far right, and select 'Displays'. Note that there are not many resolutions available, but you can use full-screen mode which will change the resolution to your host machine's resolution.
* To set up printing: it's probably easiest to print to a PDF, transfer that file to your host machine (see below), and print from your host machine.
* To load up a file manager (like Windows Explorer): from the 'Files' menu (upper-left of the screen), select 'Home Folder'

###Transferring files back and forth

The easiest solution may be the last one listed here, so read through these before you start on any of them.

One option is to set up an e-mail client (or use a web browser - firefox is installed, and the icon is on the top menu bar) and e-mail your files back and forth. Or use an online file server.

You can also set up 'shared folders' to directly read and write files back and forth. To do this:

* Find the VirtualBox toolbar at the bottom (this is not the Gnome toolbar at the bottom, but the toolbar that appears when you are not in full-screen mode). Right-click on the icon that looks like a blue folder, and select 'shared folders'.
* Configure one (or more) shared folders. You will need to select a name for the shared folder and the directory that it reads from and writes to. Select the Auto-mount option.

## Unix

*Be sure to follow along as you learn about different commands in the terminal. You will need to show what you have done in the terminal at the end of the lab.*

Unix is a very powerful operating system that has been around, in one form or another, for almost 40 years. The fact that it still exists attests to how powerful it can be for completing tasks on a computer. The reason it is not more widely adopted is because it is not very easy to use or intuitive -- it was written by computer programmers for computer programmers. While the people in this course are certainly capable of learning it, many people just want a computer to work, and to run an Office suite and a set of Internet programs such as a browser. For those users, an easier to use operating system (such as Windows or Mac OS X) is often better. Unix is coming more into the mainstream lately with the increased popularity of Linux, as well as the fact that Mac OS X is built upon a Unix operating system (FreeBSD, in particular).

The word 'Unix' can mean any Unix-like operating system. There are many available -- Linux, FreeBSD, Solaris, Mac OSX, etc. We will be using the word Unix in this class to mean whichever Unix-like environment we are using for this course.

A quick note: Unix IS CASE SENSITIVE. Thus, foo, Foo, FOO, and FoO are all different, and allowable, file names. This causes problems with Windows, which sees all those names as the same thing. So be careful about your cases!

###Files
Everything in UNIX is either a file or a process.

* A process is an executing program identified by a unique PID (process identifier).
* A file is a collection of data. They are created by users using text editors, running compilers etc.

All the files are grouped together in the directory structure. The file-system is arranged in a hierarchical structure, like an inverted tree. The top of the hierarchy is traditionally called **root** (written as a slash / ).  For example, the path "/home/student/hello.c" refers to the file hello.c in the student directory, which is directly under root.

###Command Line Interface
In the command line interface, instead of using graphical user interfaces, you type text commands to tell the computer what to do.

To load a terminal (a.k.a. command prompt or shell): click the search button at the upper left corner, then search for **Terminal**. The terminal should show a prompt that ends with the **$** symbol.  The terminal is a command line interpreter (CLI). It interprets the commands the user types in and arranges for them to be carried out. The commands are themselves programs: when they terminate, the terminal gives the user another prompt ($ on our systems).

* *Filename Completion* - By typing part of the name of a command, filename or directory and pressing the **[Tab]** key, the terminal will complete the rest of the name automatically. 
* *History* - The terminal keeps a list of the commands you have typed in. If you need to repeat a command, use the cursor keys to scroll up and down the list or type history for a list of previous commands.

#### Getting Help

There are on-line manuals which gives information about most commands. The manual pages tell you which options a particular command can take, and how each option modifies the behaviour of the command. Type man command to read the manual page for a particular command.

For example, to find out more about the wc (word count) command, type

    $ man wc

Alternatively

    $ whatis wc

gives a one-line description of the command, but omits any information about options etc.

When you are not sure of the exact name of a command,

    $ apropos keyword

will give you the commands with keyword in their manual page header. For example, try typing

    $ apropos copy

####Listing files and directories
When you first login, your current working directory is your home directory. Your home directory has the same name as your user-name, and it is where your personal files and subdirectories are saved.

To find out what is in your home directory, type

    $ ls

The `ls` command ( lowercase L and lowercase S ) lists the contents of your current working directory.

`ls` does not, in fact, cause all the files in your home directory to be listed, but only those ones whose name does not begin with a dot (.) Files beginning with a dot (.) are known as hidden files and usually contain important program configuration information. They are hidden because you should not change them unless you are very familiar with UNIX!!!

To list all files in your home directory including those whose names begin with a dot, type

    $ ls -a

####Clearing the Screen
At the prompt, type

    $ clear

This will clear all text and leave you with the prompt at the top of the window.

####Making Directories

We will now make a subdirectory in your home directory to hold the files you will be creating and using in the course of this lab. To make a subdirectory called _unixstuff_ in your current working directory, type

    $ mkdir unixstuff

To see the directory you have just created, type

    $ ls

####Changing to a different directory 

The command `cd directory` means change the current working directory to 'directory'. The current working directory may be thought of as the directory you are in, i.e. your current position in the file-system tree.

To change to the directory you have just made, type

    $ cd unixstuff

Type `ls` to see the contents (which should be empty).

**EXERCISE**: Make another directory inside the _unixstuff_ directory called _backups_.

####The directories . and ..
Still in the _unixstuff_ directory, type

    $ ls -a

As you can see, in the _unixstuff_ directory (and in all other directories), there are two special directories called (.) and (..)

#####The current directory (.)

In UNIX, (.) means the current directory, so typing

    $ cd .

_NOTE_: there is a space between cd and the dot

means stay where you are (the _unixstuff_ directory).

This may not seem very useful at first, but using (.) as the name of the current directory will save a lot of typing, as we shall see later in the tutorial.

#####The parent directory (..)

(..) means the parent of the current directory, so typing

    $ cd ..

will take you one directory up the hierarchy (back to your home directory). Try it now.

Note: typing `cd` with no argument always returns you to your home directory. This is very useful if you are lost in the file system.

####Pathnames
Pathnames enable you to work out where you are in relation to the whole file-system. For example, to find out the absolute pathname of your home-directory, type `cd` to get back to your home-directory and then type

    $ pwd

**Exercise**: Use the commands `cd`, `ls`, and `pwd` to explore the file system.

####Touch
This program creates a new empty file (or "touches" existing files to update their modification time).

    $ touch filename

**Exercise**: Use `touch` to create a new file called "notes.txt" inside _unixstuff_.

####More about home directories and pathnames
#####Understanding pathnames

First type `cd` to get back to your home-directory, then type

    $ ls unixstuff

to list the contents of your _unixstuff_ directory.

Now type

    $ ls backups

You will get a message like this -

    backups: No such file or directory

The reason is, _backups_ is not in your current working directory. To use a command on a file (or directory) not in the current working directory (the directory you are currently in), you must either `cd` to the correct directory, or specify its full pathname. To list the contents of your backups directory, you must type

    $ ls unixstuff/backups

#####~ (your home directory)

Home directories can also be referred to by the tilde ~ character. It can be used to specify paths starting at your home directory. So typing

    $ ls ~/unixstuff

will list the contents of your unixstuff directory, no matter where you currently are in the file system.

**Exercise**: Answer the following questions:

What does this following command list?

    $ ls ~

How about this one?

    $ ls ~/..

##### Copying Files

`cp file1 file2` is the command which makes a copy of _file1_ in the current working directory and calls it _file2_.

Type

    $ cp notes.txt notes1.txt

to make a copy of notes.txt.

##### Moving Files
`mv file1 file2` moves (or renames) _file1_ to _file2_

To move a file from one place to another, use the `mv` command. This has the effect of moving rather than copying the file, so you end up with only one file rather than two.

It can also be used to rename a file, by moving the file to the same directory, but giving it a different name.

Type 

    $ mv notes.txt notes0.txt

to rename notes.txt.

##### Removing Files and Directories

To delete (remove) a file, use the `rm` command. 

You can use the `rmdir` command to remove a directory (make sure it is empty first). 

**Exercise**: Use the `rm` command to remove _notes0.txt_ that you created previously.  Create a directory called _tempstuff_ using `mkdir`, then remove it using the `rmdir` command.

#### Editing a Text File
There are a number of editors that are installed on the system.  One is [*gedit*](https://wiki.gnome.org/Apps/Gedit), which is a simple text editor for the GNOME desktop.

Type

    $ gedit notes1.txt&

to open _notes1.txt_ in gedit. By appending & at the end of the command above, gedit is opened in the background so that the shell does not have to wait for gedit to finish.

Put some text (at least 50 lines--you can copy and paste some random text from a web page) in _notes1.txt_ and save the file. Experiment with the features in gedit. It should be straightforward to use. 

Two popular text editors among programmers are [emacs](http://www.gnu.org/software/emacs/) and [vi](http://www.vim.org/). Both allow efficient text editing.  Explore both editors to see how they work. There are plenty of online tutorials that you can reference. I highly recommend that you get familiar with at least one of these editors.

####Displaying the contents of a file on the screen
The command `cat` can be used to display the contents of a file on the screen. Type:

    $ cat notes1.txt

The command `less` writes the contents of a file onto the screen a page at a time. Type

    $ less notes1.txt

Press the [space-bar] if you want to see another page, and type [q] if you want to quit reading. As you can see, `less` is used in preference to cat for long files.

The `head` command writes the first ten lines of a file to the screen.

The `tail` command writes the last ten lines of a file to the screen.

## Turning in this Lab

At this point, your home directory should contain the following:

* unixstuff
* unixstuff/backups
* unixstuff/notes1.txt

To get credits for this lab, show your terminal with the commands you used in this lab to the instructor. The instructor will ask you to demonstrate some of the commands that you have learned in this lab (e.g. cd, ls, rm, rmdir, gedit, etc.).  The instructor will also ask for you github username, which will be used for access to your repository for this course.  If you do not have a github account, be sure to [join github](https://github.com/join) before you ask to get checked off.
