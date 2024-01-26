##  Searching for Text in Files Using `findstr`

The command `findstr` is used in the Windows command line environment to search for patterns in files. Here's a breakdown of the command

<pre> findstr /s /i "data" *.txt` </pre>

- `findstr`: This is the command used to search for text within files.  
- `/s`: This flag tells `findstr` to search for the specified string in the current directory and all its subdirectories (recursively).  
- `/i`: This flag makes the search case-insensitive, meaning it will match "data", "Data", "DATA", etc.
- `"data"`: This is the string we are searching for within the files.
- `*.txt`: This part specifies the file type to search in. In this case, `*.txt` means all files with a `.txt` extension.

When this command is run, it will search every text file in the current directory and its subdirectories for the string "data", regardless of the case, and display the lines where the string is found along with their file paths. 

## Nbstripout

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


## MLflow

<pre> mlflow ui --backend-store-uri /path/to/folder </pre>

<pre> mlflow ui --backend-store-uri /path/to/folder --host server name --port number </pre> 

## Jupyter Notebook on Server

<pre> jupyter notebook --ip 0.0.0.0 </pre> 



