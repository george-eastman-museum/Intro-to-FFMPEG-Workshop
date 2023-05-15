#######################
Command Line Basics
#######################

********************************
Navigation
********************************

whoami
========================================

Prints the user that is you are currently executing commands as.

.. tabs::
   .. group-tab:: MacOS
      .. code-block:: bash
         
         whoami
         
   .. group-tab:: Linux
      .. code-block:: bash
         
         whoami
         
   .. group-tab:: Windows
      .. code-block:: bash
         
         whoami
         
Print Working Directory
========================================

Prints the full path of the current "working" directory. This is where you are currently running commands from.

.. tabs::
   .. group-tab:: MacOS
      .. code-block:: bash
      
         pwd
         
   .. group-tab:: Linux
      .. code-block:: bash
      
         pwd
         
   .. group-tab:: Windows
      .. code-block:: bash
      
         cd

Change Directories
========================================

We can navigate folders on our computer from the command line using the ``cd`` command similar to how we would in a GUI file browser.

.. tabs::
   .. group-tab:: MacOS

      Change directories to Downloads folder.

      .. code-block:: bash
      
         cd /home/myUsername/Downloads

      Change directories to current User's home directory.

      .. code-block:: bash
      
         cd ~

      Go back one folder level.

      .. code-block:: bash

         cd ..
         

   .. group-tab:: Linux

      Change directories to Downloads folder.

      .. code-block:: bash
      
         cd /home/myUsername/Downloads

      Change directories to current User's home directory.

      .. code-block:: bash
      
         cd ~

      Go back one folder level.

      .. code-block:: bash

         cd ..
         

   .. group-tab:: Windows

      Change directories to Downloads folder.

      .. code-block:: bash
      
         cd C:\Downloads
         
      When changing between different drives, include `/d`.

      .. code-block:: bash

         cd /d D:\Directory

      Go back one folder level.

      .. code-block:: bash

         cd ..


List Folder Contents
========================================

Lists the contents of the current working directory. If you follow the command with the path to a different directory, it will list the contents of that directory instead.

.. tabs::
   .. group-tab:: MacOS

      List current folder contents

      .. code-block:: bash
      
         ls
         
      List contents of Documents folder

      .. code-block:: bash
      
         ls "/home/myUsername/Documents"
         

   .. group-tab:: Linux

      List current folder contents
      
      .. code-block:: bash
      
         ls
         
      List contents of Documents folder

      .. code-block:: bash
      
         ls "/home/myUsername/Documents"
         

   .. group-tab:: Windows

      List current folder contents

      .. code-block:: bash
      
         dir
         
      List contents of My Documents folder

      .. code-block:: bash
      
         dir "C:\Users\myUsername\Documents"
         

Notes About Quotes
========================================

The command line uses spaces to separate various parts of commands. As a result, file and folder paths that contain spaces need to be handled in special ways to ensure that those spaces are correctly read as part of a larger string of text rather than separators within the command. A common way to accomplish this is to enclose the path in single (``''``) or double (``""``) quotes.

.. tabs::
   .. group-tab:: MacOS
      .. code-block:: bash
      
         cd "/home/myUsername/path with spaces"
         

   .. group-tab:: Linux
      .. code-block:: bash
      
         cd "/home/myUsername/path with spaces"
         

   .. group-tab:: Windows
      .. code-block:: bash
      
         cd "C:\Users\myUsername\path with spaces"

- Another way to handle spaces is by "escaping" them using a special character (``\``) that tells the command line to ignore its usual interpretation of whatever immediately follows that character. This might look something like ``/home/myUsername/path\ with\ spaces``

- You'll notice that when you drag and drop files with spaces in the path or filename onto the command line, the resulting path will always be formatted in a way that handles the spaces appropriately (either enclosing the text in quotes or inserting escape characters before each space).

- Be careful when copying quoted paths/filenames from certain sources, such as Word documents or spreadsheets, as these types of documents may format text in ways that can cause issues for commands. For example, the following single (``‘’``) and double (``“”``) quotes will NOT work.

********************************
Wildcards
********************************

Certain special characters (``?``, ``!``, ``[]``, ``*``) are used to match patterns. This can be very useful when trying to run a command on a certain subset of files or folders that share certain identifying characteristics. One example of a very common wildcard is ``*``, which matches any combination of characters.

.. tabs::
   .. group-tab:: MacOS

      List all .mp4 files in the current directory

      .. code-block:: bash
      
         ls *.mov

      List all .mp3 files in every folder in the Music directory

      .. code-block:: bash
      
         ls /home/myUsername/Music/*/*.mp3


   .. group-tab:: Linux

      List all .mp4 files in the current directory.

      .. code-block:: bash
      
         ls *.mp4

      List all .mp3 files in every folder in the Music directory.

      .. code-block:: bash
      
         ls /home/myUsername/Music/*/*.mp3


   .. group-tab:: Windows

      List all .mp4 files in the current directory.

      .. code-block:: bash
      
         dir *.mp4
         
      List all .mp3 files in every folder in the Music directory.

      .. code-block:: bash
      
         dir C:\Users\myUsername\Music\*\*.mp3

********************************
Redirects and Pipes
********************************

Pipe
========================================

Pipes (``|``) are used to pass the output from one command to another program.

Redirect
========================================

Redirects (``>``, ``<`` or ``>>``, ``<<`` to append) are used to pass the output from one command to a file or stream.

.. tabs::
   .. group-tab:: MacOS
      .. code-block:: bash
      
         ls > file_list.txt 

   .. group-tab:: Linux
      .. code-block:: bash
      
         ls > file_list.txt

   .. group-tab:: Windows
      .. code-block:: bash
      
         dir > file_list.txt

********************************
Combining Commands
********************************

Performing Commands Sequentially
========================================

Commands can be set to execute one after another. This allows us to queue up a number of commands to run in sequence.

.. tabs::
   .. group-tab:: MacOS
      .. code-block:: bash
      
         command1 ; command2
         
   .. group-tab:: Linux
      .. code-block:: bash
      
         command1 ; command2
         
   .. group-tab:: Windows
      .. code-block:: bash
      
         command1 & command2

Conditionally Run Commands
========================================

Commands can be set to run depending on whether the previous command succeeded (exit status = 0) or failed (non-zero exit status). This can allow us to make sequential commands that are more interdependent. If a later command depends on the output from a previous command being created successfully, we can ensure that our second command only runs if that first command successfully created the necessary output. Similarly, can build in error handling to divert commands down a different path if a previous command failed. 

.. tabs::
   .. group-tab:: MacOS

      Run command2 only if command1 completed successfuly

      .. code-block:: bash
      
         command1 && command 2

      Run command2 only if command1 failed

      .. code-block:: bash
      
         command1 || command2
         
   .. group-tab:: Linux

      Run command2 only if command1 completed successfuly

      .. code-block:: bash
      
         command1 && command2

      Run command2 only if command1 failed

      .. code-block:: bash
      
         command1 || command2
         
   .. group-tab:: Windows

      Run command2 only if command1 completed successfuly

      .. code-block:: bash
      
         command1 && command2

      Run command2 only if command1 failed

      .. code-block:: bash
      
         command1 || command2

********************************
Loops and Batch Processing
********************************

For Loops
========================================

.. tabs::
   .. group-tab:: MacOS
      .. code-block:: bash
      
         for x in /home/myUsername/example/*.flac ; do ffmpeg -i "$x" -ab 320k -f mp3 "${x//.flac}".mp3 ; done
         
   .. group-tab:: Linux
      .. code-block:: bash
      
         for x in /home/myUsername/example/*.flac ; do ffmpeg -i "$x" -ab 320k -f mp3 "${x//.flac}".mp3 ; done
         
   .. group-tab:: Windows
      .. code-block:: bash
      
         for "C:\Users\myUsername\example\" %x in (*.flac) do ffmpeg -i "%x" -ab 320k -f mp3 "%~nx.mp3"

********************************
Checksumming Files
********************************

Many operating systems include some default program that can create checksums directly from the command line.

.. tabs::
   .. group-tab:: MacOS
      .. code-block:: bash
      
         md5 input_file
         
   .. group-tab:: Linux
      .. code-block:: bash
      
         md5sum input_file
         
   .. group-tab:: Windows
      .. code-block:: bash
      
         certUtil -hashfile input_file MD5
