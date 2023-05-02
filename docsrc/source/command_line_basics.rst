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
text

.. tabs::
   .. group-tab:: MacOS
      .. code-block:: bash
      
         "/home/myUsername/path with spaces"
         
   .. group-tab:: Linux
      .. code-block:: bash
      
         "/home/myUsername/path with spaces"
         
   .. group-tab:: Windows
      .. code-block:: bash
      
         "C:\Users\myUsername\path with spaces"

**************************
3.2. Wildcards
**************************
text

**************************
3.3. Combining Commands
**************************


3.3.1. Performing Commands Sequentially
========================================

3.3.2. Conditionally Run Commands
========================================

3.3.3. Pipe
========================================

3.3.4. Redirect
========================================

**************************
3.4. Loops
**************************
