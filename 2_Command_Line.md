# Command Line Fun

## The Bash Environment
- Environment Variable
    - We can view the content of given environment variable using with the **echo** command followed by the *$* character and an environment variable name.
        - ``` $ echo $PATH ```
        - ``` $ echo $USER ```
        - ``` $ echo $HOME ```
        - ``` $ echo PWD ```
    - The **export** command makes the variable accessible to any sub-processes we might spwan from our current bash instance. If we set an environment variable without **export** it will only be available in current shell. *"$$"* variable is used to display process ID.
        - ``` $ echo $Path ```
        - ``` $ var="My variable" ```
        - ``` $ echo $var ```
        - ``` $ bash ```
        - ``` $ echo "$$" ```
        - ``` $ export othervar="Global var" ```
        - ``` $ echo $othervar ```
        - ``` $ bash ```
        - ``` $ echo $othervar ```
        - ``` $ exit ```
    - We can view other environment variables defined by **env** command 
        - ``` $ env ```
- Bash History Tricks
    - **history** command to view record of commands entered into the shell
        - ``` $ history ```
    - *History Expansion* :  To use specific command from the list, use *!* character followed by the line no. 
        - ``` $ !1 ```
    - To re-enter the last command given to shell, use *!!* followed by a **TAB**.
        - ``` $ systemctl status apache2 ```
        - ``` $ !! ```
    - Environment Variable that controls the History Size : HISTSIZE and HISTFILESIZE
        - HISTSIZE : controls no. of commands stored in memory for current session.
        - HISTFILESIZE : configures how many commands are kept in history files.
    - *reverse-i-search* : Hold CTRL + R to invoke. Type the characters to get a match of recent command in history list. Press RETURN key to execute it.
        - ``` $ <CTRL+R>apt<ENTER> ``` 
## Piping & Redirection
- Streams
    - Standard Input(STDIN) : Data fed into program
    - Standard Output(STDOUT) : Output from the program (defaults to terminal)
    - Standard Error(STDERR) : Error Messages (defaults to terminal)
- Redirecting to a new File
    - ``` $ echo "Learning Penetration Testing" > temp.txt ```
- Redirecting to an existing File
    - ``` $ echo "Appeding this additional data" >> data.txt ```
- Redirecting from a file
    - ``` $ wc -m < data.txt ```
- Redirecting standard error
    - According to POSIX specification, file descriptor for STDIN, STDOUT, STDERR are defined as 0, 1 and 2 respectively.
    - ``` $ ls .```
    - ``` $ ls ./file_not_Exist```
    - ``` $ ls ./file_not_exist 2>error.txt```
    - ``` $ cat error.txt```
- Piping
    - ``` $ cat error.txt ```
    - ``` $ cat error.txt | wc -m > count.txt```
    - ``` $ cat count.txt```
## Text Searching & Manipulation
## Editors
## Comparing Files
## Managing Processes
## File Command Monitoring
## Downloading Files
## Customizing the Bash Environment
