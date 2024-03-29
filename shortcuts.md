# Shortcuts and Commands for Data Science Project Workflow
---

## Table of Contents
1. [Searching for Text in Files Using `findstr`](#searching-for-text-in-files-using-findstr)  
2. [Cleaning Output from Jupyter Notebooks with `nbstripout`](#cleaning-output-from-jupyter-notebooks-with-nbstripout)  
3. [Partially Matching Files (Folder Paths) in UNIX](#partially-matching-files-folder-paths-in-unix) 
4. [MLflow](#mlflow)
5. [Accessing Jupyter Notebook on Server](#accessing-jupyter-notebook-on-server)
6. [Managing Background Processes with Screen](#managing-background-processes-with-screen)

---
##  Searching for Text in Files Using `findstr`

The command `findstr` is used in the Windows command line environment to search for patterns in files. Here's a breakdown of the command

<pre> findstr /s /i "data" *.txt` </pre>

- `findstr`: This is the command used to search for text within files.  
- `/s`: This flag tells `findstr` to search for the specified string in the current directory and all its subdirectories (recursively).  
- `/i`: This flag makes the search case-insensitive, meaning it will match "data", "Data", "DATA", etc.
- `"data"`: This is the string we are searching for within the files.
- `*.txt`: This part specifies the file type to search in. In this case, `*.txt` means all files with a `.txt` extension.

When this command is run, it will search every text file in the current directory and its subdirectories for the string "data", regardless of the case, and display the lines where the string is found along with their file paths. 

## Cleaning Output from Jupyter Notebooks with `nbstripout`

<pre> find path/to/notebooks/folder -name "*.ipynb" -exec nbstripout {} \; </pre>

The command provided is used in Unix-like systems to clean the output from Jupyter notebooks:

- `find`: This is the command used to search for files in a directory hierarchy.
- `path/to/notebooks/folder`: This specifies the directory path where your Jupyter notebooks are located.
- `-name "*.ipynb"`: This part of the command tells `find` to look for files that match the name pattern `*.ipynb`, which means all files with the `.ipynb` extension (Jupyter notebooks).
- `-exec`: This flag is followed by a command template that `find` will execute for each matched file.
- `nbstripout {}`: This is the command that will be executed for each found notebook. `nbstripout` is a tool that removes outputs from Jupyter notebooks, and `{}` is a placeholder for the filename that `find` substitutes into the command.
- `\;`: This signifies the end of the command template for the `-exec` action.

When this command is run, it will recursively search for all Jupyter notebook files in the specified path and execute `nbstripout` on each one, effectively removing their output content. This is particularly useful for version control purposes, as it reduces the amount of non-essential data in commits and makes the notebooks easier to diff.

## Partially Matching Files (Folder Paths) in UNIX

<pre> find . -name 'mlruns' </pre>

- `find` is a command-line utility for searching file systems.
-`.` specifies the current directory as the starting point for the search.
- `name` tells find to look for files or directories matching the given name.
- `'mlruns'` is the name of the directories you're searching for.


## MLflow

<pre> mlflow ui --backend-store-uri /path/to/folder </pre>

<pre> mlflow ui --backend-store-uri /path/to/folder --host server name --port number </pre> 

## Accessing Jupyter Notebook on Server

Utilize the command below to seamlessly access your Jupyter Notebook hosted on a server. This setup enhances your ability to interact with and manage files with greater flexibility and convenience.

<pre> jupyter notebook --ip 0.0.0.0 </pre> 

This command configures the Jupyter Notebook to listen on all available IP addresses of the server, making it accessible from any network interface. It's an ideal approach for remote data analysis, enabling you to work with your notebooks from anywhere, as long as you have network access to the server.

## Managing Background Processes with Screen

### Creating a Screen Session

1. Create a new screen session where you can run your processes in the background, use the following command. Replace `<screen_name_arbitrary>` with a name that makes sense for your session:

<pre> screen -S `screen_name_arbitrary` </pre> 

After executing this command, you'll be placed into a new terminal session where you can set environment variables and run commands as needed.

2. Inside the screen, you can now run any command or process you need. Set up your environment variables as necessary before executing your desired command.

### Detaching from Screen

To detach from the screen session and return to your original terminal, press **`CTRL + A`** followed by **`D`**. Your process will continue to run in the background.

### Terminating a Screen

To terminate a screen, type:

<pre> CTRL + D </pre>

When you're inside a screen session and you've closed all running applications, you can simply press **`CTRL + D`** to exit the screen session. If it's the last terminal within your screen session, this command will effectively terminate the session.

### Managing Screen Sessions

If you need to see a list of all your active screen sessions, type:

<pre> screen -ls </pre>

This command will display all current screen sessions, allowing you to identify the session you may want to reattach to.

### Reattaching to a Screen Session

To reattach to a specific screen session, use the following command with the name or ID of the session you want to access:

<pre> screen -r `session_name_or_ID` </pre> 

