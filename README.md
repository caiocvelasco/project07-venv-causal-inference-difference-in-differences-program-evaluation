# Causal Inference Method (Difference-in-Differences): Measuring the Effect of a new Customer-Satisfaction Program at an Airline Company
* To check the Notebook for the Airline Project, go to its folder above (`airline_project`)

<img src = "airline_project\img\airline.jpg">

## Table of Contents

- [Project Structure](#project-structure)
- [The Project](#the-project)
- [Setup Instructions](#setup-instructions)
  - [Prerequisites](#prerequisites)
  - [Build and Run](#build-and-run)

## Project Structure

- **my_project (project-root)/**
    - **.venv/**
    - **data/**
      - datasets.csv
    - **img/**                   
    - **.gitignore**             (A file to ignore what should not be pushed to the repo)
    - **.python-version**        (A file to control the python version being used in this project)
    - **requirements.txt**       (A file to install all needed dependencies)
    - **README.md**

## The Project

This project analyzes data from a customer satisfaction experiment conducted across four types of airports in Brazil, involving 192 participants. The experiment's purpose is to evaluate the impact of a new counter service protocol, `CounterXP`: Counter Experience, on customer satisfaction, measured by the Net Promoter Score (NPS) on a scale of 0 to 100. Passengers with similar characteristics were matched to control for covariates. Additionally, each passenger's last NPS score prior to the intervention (within the last 30 days) was recorded for comparison.

The airports are classified based on operational demand levels:

* **High Demand**: International airports with high passenger volume, including a significant number of connections.
* **Medium-High Demand**: Primarily international airports with average passenger volume.
* **Medium-Low Demand**: Primarily national airports with moderate passenger volume.
* **Low Demand**: National airports with lower passenger traffic.

`CounterXP` leverages machine learning recommendations to streamline check-in by tailoring suggestions for special accommodations to enhance the passenger experience. Positive outcomes from this pilot could lead to the broader implementation of this protocol across additional operational contexts.

## Setup Instructions

### Prerequisites

Make sure you have the following installed on your local development environment:

* [VSCode](https://code.visualstudio.com/)
  * Install `GitLens — Git supercharged` extension and Jupyter Notebook extensions.
* [Pyenv](https://github.com/pyenv-win/pyenv-win)
  * This will manage your Global Python Version (on your machine) and Local Python Versions (for your project).
  * Open Windows Powershell and follow the instructions from the Pyenv website, which are:
    * `Invoke-WebRequest -UseBasicParsing -Uri "https://raw.githubusercontent.com/pyenv-win/pyenv-win/master/pyenv-win/install-pyenv-win.ps1" -OutFile "./install-pyenv-win.ps1"; &"./install-pyenv-win.ps1"`
  * If there is an error, try this:
    * `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`
  * Then, try the command above again
  * Open Git Bash:
    * pyenv --version (This will show if pyenv was installed successfully)
  * Create Pyenv Environment Variables in Windows
    * Windows Flag on your Keyboard + R:
      * sysdm.cpl -> Advanced Tab -> Environment Variables
      * Get the `pyenv-win` folder path. Usually, it is created here: `C:\Users\YOUR_USER\.pyenv\pyenv-win\`
      * Create 3 variables in the "User variables for YOUR_USER" part, and put the path above to each of them:
        * PYENV, PYENV_ROOT, PYENV_HOME
      * Double-click `Path` in the same part and click on New and add the paths for `bin` and for `shims`
        * `C:\Users\caiov\.pyenv\pyenv-win\bin`
        * `C:\Users\caiov\.pyenv\pyenv-win\shims`
        * Move both of them to the top (This will allow pyenv to have preference over the other python interpreters)
    * Check if it is working: Git Bash -> pyenv
  * Install Python Versions (This will install the python version that will be linked to different project with pyenv)
    * pyenv install 3.12.1
    * pyenv install 3.9.13
    * Check with: pyenv versions
  * Configure the Global Python version for your machine:
    * pyenv global 3.12.1
    * pyenv global (This will show the current global python version)
  * Configure the Local Python version for your project 
    * cd your_repo_folder
    * pyenv local 3.9.13 (This will create a `.python-version` file in your repo folder with the local version of your project)
    * Check with: python --version
* [.venv - Virtual Environment](https://docs.python.org/3/library/venv.html)
  * cd your_repo_folder:
    * cd "C:\...\latam-project"
  * python -m venv .venv           (This will create a virtual environment for the repo folder)
  * source .venv/Scripts/activate  (This will activate your virtual environment)
  * Install everything you need for your project from the `requirements.txt` file:
    * pip install --no-cache-dir -r requirements.txt  (This will install things inside your virtual environment)
    * maybe you need to update pip, this is important to avoid conflicts: python.exe -m pip install --upgrade pip
    * Check: pip list

  * [Git]
    * Make sure to inclue a .gitignore file with the following information:
      * .venv/         (to ignore the virtual environment stuff)
      * *.pyc          (to ignore python bytecode files)
      * data/          (to ignore the dataset)

### Build and Run

1. **Clone the repository:**

   ```bash
   git clone https://github.com/caiocvelasco/project07-venv-causal-inference-difference-in-differences-program-evaluation.git
   cd cd "C:\...\airline_project"

2. **Activate you Virtual Environment (.venv)**

* cd "C:\...\airline_project"
* source .venv/Scripts/activate                   (This will activate your environment)

3. **Latam Project**

* To check the project, go to its folder: `airline_project`