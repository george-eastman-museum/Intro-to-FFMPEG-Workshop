#######################
3. Command Line Basics
#######################

**************************
3.1. Navigation
**************************

3.1.1. whoami
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

3.1.2. Print Working Directory
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

3.1.3. List Folder Contents
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
         

3.1.4. Notes About Quotes
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

**************************
3.2. Wildcards
**************************
text

**************************
3.3. Combining Commands
**************************

3.3.1. Performing Commands Sequentially
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

3.3.2. Conditionally Run Commands
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

3.3.3. Pipe
========================================

Pipes are used to pass the output from one command to another program.

3.3.4. Redirect
========================================

Redirects are used to pass the output from one command to a file or stream.

**************************
3.4. Loops
**************************