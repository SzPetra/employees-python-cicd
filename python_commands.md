python -m venv ven: creates venv directory -> scripts directory with the name "ven"

pip install --editable . -> download dependencies and libraries for project
pip freeze --exclude-editable > constraints.txt
-> from now on to install -> python -m install -c constraints.txt