# Terminal Commands:

## MacOS:
note `python -m` = python module shorthand.

- `python -m venv <new_venv>` - Create new venv.
- `python3.10 -m venv <new_venv>` - Specify python version to create a venv of the python version

- `source <new_venv>/bin/activate` -  Activate virtual environment. (Make sure you specicy the right path)

## Windows
<details>
  <summary>Click for Windows commands</summary>
  1. `python -m venv {path_to_your_folder}/{venv_name}`
</details>

## Activation:

| Platform | Shell | Command to activate virtual environment |
|----------|-------|-----------------------------------------|
| POSIX   | bash/zsh | `$ source <venv>/bin/activate` |
| POSIX   | fish | `$ source <venv>/bin/activate.fish` |
| POSIX   | csh/tcsh | `$ source <venv>/bin/activate.csh` |
| PowerShell | PowerShell | `$ <venv>/bin/Activate.ps1` |
| Windows | cmd.exe | `C:\> <venv>\Scripts\activate.bat` |
| Windows | PowerShell | `PS C:\> <venv>\Scripts\Activate.ps1` |

## Get Jupyter Venv working on the platform

- `pip install ipykernel` - 
- `python3 -m ipykernel install --user --name=<new_venv>` - Register this venv with jupyter lab. Will need to refresh the page to ensure the new venv is available from the dropdown. Add `--display-name "Python (new-venv)"` at the end of the `ipykernel install command` to change the display name of the venv created.


- `jupyter kernelspec list` - list all of the availabile kernels and their paths
- `jupyter kernelspec uninstall <unwanted-kernel>` - uninstall unwanted kernel, will be prompted [y/N] in terminal before it's ran completely;.
- 

## Adding Venv to VSCode Jupyter Notebook Kernel:
When creating venv's in VS Code, sometimes the kernel will automatically be detected in Jupyter Notebooks. Where it doesn't detect this automatically, try these steps

Note you will to install ipykernel in your venv, and then add your new venv to the jupyter kernels.

1) Press Command+Shift+P to open a new command pallete
2) Select > Python: Select Intepreter to start jupyter notebook server
          > Select Interpreter Path
          > Find - navigate to python3 version (e.g. python3.11) in bin folder
3) - Close & ReOpen the notebook again
   - or Restart VS Code for the changes to take effect.

