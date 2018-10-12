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
        
        
  






