Jupyter Terminal Commands:

note `python -m` = python module shorthand.

- `python -m venv <new_venv>` - Create new venv.
- `python3.10 -m venv <new_venv>` - Specify python version to create a venv of the python version

- `source <new_venv>/bin/activate` -  Activate virtual environment. (Make sure you specicy the right path)

## Get Jupyter Venv working on the platform

- `pip install ipykernel` - 
- `python3 -m ipykernel install --user --name=<new_venv>` - Register this venv with jupyter lab. Will need to refresh the page to ensure the new venv is available from the dropdown. Add `--display-name "Python (new-venv)"` at the end of the `ipykernel install command` to change the display name of the venv created.


- `jupyter kernelspec list` - list all of the availabile kernels and their paths
- `jupyter kernelspec uninstall <unwanted-kernel>` - uninstall unwanted kernel, will be prompted [y/N] in terminal before it's ran completely;.
- 

## Adding Venv to VSCode Jupyter Notebook Kernel:
When creating venv's in VS Code, sometimes the kernel will automatically be detected in Jupyter Notebooks. Where it doesn't detect this automatically, try these steps

1) Press Command+Shift+P to open a new command pallete
2) Select > Python: Select Intepreter to start jupyter notebook server
          > Select Interpreter Path
          > Find - navigate to python3 version (e.g. python3.11) in bin folder
3) - Close & ReOpen the notebook again
   - or Restart VS Code for the changes to take effect.


## Generate requirements file:

- `pip list --format=freeze > requirements.txt` - to generate only packages being used in the current project. (Make sure to sure command whilst your VENV is activatedl!
- 
