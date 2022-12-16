Jupyter Terminal Commands:

- `python -m venv <new_venv>` - Create new venv.
- `python3.10 -m venv <new_venv>` - Specify python version to create a venv of the python version

- `source <new_venv>/bin/activate` -  Activate virtual environment.

- `pip install ipykernel` - 
- `python3 -m ipykernel install --user --name=<new_venv>` - Register this venv with jupyter lab. Will need to refresh the page to ensure the new venv is available from the dropdown. Add `--display-name "Python (new-venv)"` at the end of the `ipykernel install command` to change the display name of the venv created.
