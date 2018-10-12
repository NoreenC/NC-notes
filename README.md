# NC-notes
Noreen's notes repository

In terminal:
  $ is the "shell prompt" - means terminal is ready to accept commands
  in tutorial, used "ls" command - this command is used to list the files in the current directory
  "pwd" command means print working directory
  In Codecademy courses, your working directory is usually inside the home/ccuser/workspace/ directory.
  Together with ls, the pwd command is useful to show where you are in the filesystem
  cd stands for "change directory". 
  When a file, directory or program is passed into a command, it is called an argument. Here the 2015 directory is an argument for    the cd command.
  To move up one directory, use cd ... 
  The mkdir command stands for "make directory". It takes in a directory name as an argument, and then creates a new directory in the current working directory
  The touch command creates a new file inside the working directory. It takes in a filename as an argument, and then creates an empty file in the current working directory
  
  With 'ls' command:
    The -a is called an option. Options modify the behavior of commands. Here we used ls -a to display the 
    contents of the working directory in more detail.

    In addition to -a, the ls command has several more options. Here are three common options:

     -a - lists all contents, including hidden files and directories
     -l - lists all contents of a directory in long format
     -t - order files and directories by the time they were last modified.
     
     In addition to using each option separately, like ls -a or ls -l, multiple options can be used together, like ls -alt.

    Here, ls -alt lists all contents, including hidden files and directories, in long format, ordered by the date 
    and time they were    last modified.
    
    cp command:
      In addition to using filenames as arguments, we can use special characters like * to select groups of files. 
      These special characters are called wildcards. The * selects all files in the working directory, so here we 
      use cp to copy all files into the satire/ directory
      
    mv command:
    To move a file into a directory, use mv with the source file as the first argument and the destination 
    directory as the second argument. Here we move superman.txt into superhero/.

        mv wonderwoman.txt batman.txt superhero/
        
     To move multiple files into a directory, use mv with a list of source files as the first arguments, and 
     the destination directory as the last argument. Here, we move wonderwoman.txt and batman.txt into superhero/.

        mv batman.txt spiderman.txt

     To rename a file, use mv with the old file as the first argument and the new file as the second argument. 
     By moving batman.txt into spiderman.txt, we rename the file as spiderman.txt.
     
     rm
        rm waterboy.txt
        The rm command deletes files and directories. Here we remove the file waterboy.txt from the filesystem.

        rm -r comedy
        The -r is an option that modifies the behavior of the rm command. The -r stands for "recursive," 
        and it's used to delete a directory and all of its child directories.

        Be careful when you use rm! It deletes files and directories permanently. 
        There isn't an undelete command, so once you delete a file or directory with rm, it's gone.
        
        Summary of commands:
        
        You learned how to use the command line to view and manipulate the filesystem. What can we generalize so far?

          Options modify the behavior of commands:
          ls -a lists all contents of a directory, including hidden files and directories
          ls -l lists all contents in long format
          ls -t orders files and directories by the time they were last modified
          Multiple options can be used together, like ls -alt
          From the command line, you can also copy, move, and remove files and directories:
          cp copies files
          mv moves and renames files
          rm removes files
          rm -r removes directories
          Wildcards are useful for selecting groups of files and directories
          
          stdin, stdout, and stderr
            What happens when you type this command?

            $ echo "Hello"
            Hello
            The echo command accepts the string "Hello" as standard input, and echoes the string "Hello" back to the terminal             as standard output.

            Let's learn more about standard input, standard output, and standard error:

            standard input, abbreviated as stdin, is information inputted into the terminal through the keyboard or input                 device.

            standard output, abbreviated as stdout, is the information outputted after a process is run.

            standard error, abbreviated as stderr, is an error message outputted by a failed process.

            Redirection reroutes standard input, standard output, and standard error to or from a different location.
            
        $ cat hello.txt
              The cat command outputs the contents of a file to the terminal. When you type cat hello.txt, the contents of                  hello.txt are displayed.
              
        $ cat glaciers.txt >> rivers.txt
              >> takes the standard output of the command on the left and appends (adds) it to the file on the right. 
              You can view the output data of the file with cat and the filename.
              
        <
              $ cat < lakes.txt
              < takes the standard input from the file on the right and inputs it into the program on the left. 
              Here, lakes.txt is the standard input for the cat command. The standard output appears in the terminal.
   
        |
              $ cat volcanoes.txt | wc
              | is a "pipe". The | takes the standard output of the command on the left, and pipes it as standard 
              input to the command on the right. You can think of this as "command to command" redirection.

              Here the output of cat volcanoes.txt is the standard input of wc. in turn, the wc command outputs
              the number of lines, words, and characters in volcanoes.txt, respectively.

              $ cat volcanoes.txt | wc | cat > islands.txt
              Multiple |s can be chained together. Here the standard output of cat volcanoes.txt is "piped" 
              to the wc command. The standard output of wc is then "piped" to cat. Finally, the standard 
              output of cat is redirected to islands.txt.
  
        sort
              $ sort lakes.txt
              sort takes the standard input and orders it alphabetically for the standard output. Here, the lakes 
              in sort lakes.txt are  listed in alphabetical order.

              $ cat lakes.txt | sort > sorted-lakes.txt
              Here, the command takes the standard output from cat lakes.txt and "pipes" it to sort. 
              The standard output of sort is redirected to sorted-lakes.txt.

              You can view the output data by typing cat on the file sorted-lakes.txt
              
        uniq
              $ uniq deserts.txt
              uniq stands for "unique" and filters out adjacent, duplicate lines in a file. Here uniq deserts.txt 
              filters out duplicates of "Sahara Desert", because the duplicate of 'Sahara Desert' directly follows 
              the previous instance. The "Kalahari Desert" duplicates are not adjacent, and thus remain.

              $ sort deserts.txt | uniq
              A more effective way to call uniq is to call sort to alphabetize a file, and "pipe" the standard output 
              to uniq. Here by piping sort deserts.txt to uniq, all duplicate lines are alphabetized (and thereby made                      adjacent) and filtered out.
              
              sort deserts.txt | uniq > uniq-deserts.txt
              Here we simply send filtered contents to uniq-deserts.txt, which you can view with the cat command.
              
        grep I
              $ grep Mount mountains.txt
              grep stands for "global regular expression print". It searches files for lines that match a pattern 
              and returns the results.  It is also case sensitive. Here, grep searches for "Mount" in mountains.txt.

              $ grep -i Mount mountains.txt
              grep -i enables the command to be case insensitive. Here, grep searches for capital or lowercase strings that                 match Mount in mountains.txt.

              The above commands are a great way to get started with grep. If you are familiar with regular expressions, 
              you can use regular expressions to search for patterns in files.


        grep II
              $ grep -R Arctic /home/ccuser/workspace/geography
              grep -R searches all files in a directory and outputs filenames and lines containing matched results. 
              -R stands for "recursive". Here grep -R searches the /home/ccuser/workspace/geography directory for the 
              string "Arctic" and outputs filenames and lines with matched results.

              $ grep -Rl Arctic /home/ccuser/workspace/geography
              grep -Rl searches all files in a directory and outputs only filenames with matched results. 
              -R stands for "recursive" and l stands for "files with matches". Here grep -Rl searches 
              the /home/ccuser/workspace/geography directory for the string "Arctic" and outputs filenames 
              with matched results.


        grep II
              $ grep -R Arctic /home/ccuser/workspace/geography
              grep -R searches all files in a directory and outputs filenames and lines containing matched results. 
              -R stands for "recursive". Here grep -R searches the /home/ccuser/workspace/geography directory for the 
              string "Arctic" and outputs filenames and lines with matched results.

              $ grep -Rl Arctic /home/ccuser/workspace/geography
              grep -Rl searches all files in a directory and outputs only filenames with matched results. 
              -R stands for "recursive" and l stands for "files with matches". Here grep -Rl searches 
              the /home/ccuser/workspace/geography directory for the string "Arctic" and outputs filenames 
              with matched results.
              
        sed
              $ sed 's/snow/rain/' forests.txt
              sed stands for "stream editor". It accepts standard input and modifies it based on an expression, 
              before displaying it as output data. It is similar to "find and replace".

              Let's look at the expression 's/snow/rain/':

              s: stands for "substitution". it is always used when using sed for substitution.
              snow: the search string, the text to find.
              rain: the replacement string, the text to add in place.
              In this case, sed searches forests.txt for the word "snow" and replaces it with "rain." 
              Importantly, the above command will only replace the first instance of "snow" on a line.
              
              $ sed 's/snow/rain/g' forests.txt
              The above command uses the g expression, meaning "global". Here sed searches forests.txt for the 
              word "snow" and replaces it with "rain", globally. All instances of "snow" on a line will be turned to "rain".
              
    REDIRECTION
        Generalizations
        Congratulations! You learned how to use the command line to redirect standard input and standard output. 
        What can we generalize so far?

        Redirection reroutes standard input, standard output, and standard error.

        The common redirection commands are:

        > redirects standard output of a command to a file, overwriting previous content.
        >> redirects standard output of a command to a file, appending new content to old content.
        < redirects standard input to a command.
        | redirects standard output of a command to another command.
        A number of other commands are powerful when combined with redirection commands:

        sort: sorts lines of text alphabetically.
        uniq: filters duplicate, adjacent lines of text.
        grep: searches for a text pattern and outputs it.
        sed : searches for a text pattern, modifies it, and outputs it.
        
ENVIRONMENT
    Environment
    Each time we launch the terminal application, it creates a new session. The session immediately loads settings
    and preferences that make up the command line environment.

    We can configure the environment to support the commands and programs we create. This enables us to customize 
    greetings and command aliases, and create variables to share across commands and programs
    
    nano
        Nice. You just edited a file in the nano text editor. How does it work?

        $ nano hello.txt
        nano is a command line text editor. It works just like a desktop text editor like TextEdit or Notepad, 
        except that it is accessible from the command line and only accepts keyboard input.

        The command nano hello.txt opens a new text file named hello.txt in the nano text editor.
        "Hello, I am nano" is a text string entered in nano through the cursor.
        The menu of keyboard commands at the bottom of the window allow us to save changes to hello.txt 
        and exit nano. The ^ stands for the Ctrl key.

        Ctrl + O saves a file. 'O' stands for output.

        Ctrl + X exits the nano program. 'X' stands for exit.
        Ctrl + G opens a help menu.
        clear clears the terminal window, moving the command prompt to the top of the screen.
        
    ENVIRONMENT
    Bash Profile
      You created a file in nano called ~/.bash_profile and added a greeting. How does this work?

      $ nano ~/.bash_profile
      ~/.bash_profile is the name of file used to store environment settings. It is commonly called the "bash profile". 
      When a session starts, it will load the contents of the bash profile before executing commands.

      The ~ represents the user's home directory.
      The . indicates a hidden file.
      The name ~/.bash_profile is important, since this is how the command line recognizes the bash profile.
      The command nano ~/.bash_profile opens up ~/.bash_profile in nano.
      The text echo "Welcome, Jane Doe" creates a greeting in the bash profile, which is saved. It tells the 
      command line to echo the string "Welcome, Jane Doe" when a terminal session begins.
      The command source ~/.bash_profile activates the changes in ~/.bash_profile for the current session. 
      Instead of closing the terminal and needing to start a new session, source makes the changes available
      right away in the session we are in.
      
    ENVIRONMENT
    Aliases I
    What happens when you store this alias in ~/.bash_profile?

    alias pd="pwd"
    The alias command allows you to create keyboard shortcuts, or aliases, for commonly used commands.

    Here alias pd="pwd" creates the alias pd for the pwd command, which is then saved in the bash profile. 
    Each time you enter pd, the output will be the same as the pwd command.
    The command source ~/.bash_profile makes the alias pd available in the current session.
    Each time we open up the terminal, we can use the pd alias.
        
        
   ENVIRONMENT
    Environment Variables
    What happens when you store this in ~/.bash_profile?

    export USER="Jane Doe"
    environment variables are variables that can be used across commands and programs and hold information 
    about the environment.

    The line USER="Jane Doe" sets the environment variable USER to a name "Jane Doe". Usually the USER variable
    is set to the name of the computer's owner.
    The line export makes the variable to be available to all child sessions initiated from the session you are in. 
    This is a way to make the variable persist across programs.
    At the command line, the command echo $USER returns the value of the variable. Note that $ is always used when 
    returning a variable's value. Here, the command echo $USER returns the name set for the variable
    
  ENVIRONMENT
    PS1
    What happens when this is stored in ~/.bash_profile?

    export PS1=">> "
    PS1 is a variable that defines the makeup and style of the command prompt.

    export PS1=">> " sets the command prompt variable and exports the variable. 
    Here we change the default command prompt from $ to >>.
    After using the source command, the command line displays the new command prompt
    
  ENVIRONMENT
    HOME
    What happens when you type this command?

    $ echo $HOME
    The HOME variable is an environment variable that displays the path of the home directory. Here by typing
    echo $HOME, the terminal displays the path /home/ccuser as output.

    You can customize the HOME variable if needed, but in most cases this is not necessary.
    
  ENVIRONMENT
    PATH
    What happens when you type this command?

    $ echo $PATH

    /home/ccuser/.gem/ruby/2.0.0/bin:/usr/local/sbin:/usr/local/bin:/usr/bin:/usr/sbin:/sbin:/bin
    PATH is an environment variable that stores a list of directories separated by a colon. Looking carefully, 
    echo $PATH lists the following directories:

    /home/ccuser/.gem/ruby/2.0.0/bin
    /usr/local/sbin
    /usr/local/bin
    /usr/bin
    /usr/sbin
    /sbin
    /bin
    Each directory contains scripts for the command line to execute. The PATH variable simply lists which 
    directories contain scripts.

    For example, many commands we've learned are scripts stored in the /bin directory.

    /bin/pwd
    This is the script that is executed when you type the pwd command.

    /bin/ls
    This is the script that is executed when you type the ls command.

    In advanced cases, you can customize the PATH variable when adding scripts of your own.
    
  ENVIRONMENT
    env
    What happens when you type this command?

    env
    The env command stands for "environment", and returns a list of the environment variables for the current user. 
    Here, the env command returns a number of variables, including PATH, PWD, PS1, and HOME.

    env | grep PATH
    env | grep PATH is a command that displays the value of a single environment variable. Here the standard output of 
    env is "piped" to the grep command. grep searches for the value of the variable PATH and outputs it to the terminal.

    Instructions
    The commands and feature we've covered so far are commonly used to configure the environment.
    
  ENVIRONMENT
    Generalizations
    Congratulations! You learned to use the bash profile to configure the environment. What can we generalize so far?

    The environment refers to the preferences and settings of the current user.
    The nano editor is a command line text editor used to configure the environment.

    ~/.bash_profile is where environment settings are stored. You can edit this file with nano.

    environment variables are variables that can be used across commands and programs and hold information
    about the environment.

    export VARIABLE="Value" sets and exports an environment variable.
    USER is the name of the current user.
    PS1 is the command prompt.
    HOME is the home directory. It is usually not customized.
    PATH returns a colon separated list of file paths. It is customized in advanced cases.
    env returns a list of environment variables.
    
    
    
    
        
  






