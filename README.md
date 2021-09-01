# MatScIE Application

An automated tool for the extraction of methods and parameters used in the computational materials science literature.

## Description

This is a PyQT implementation of the [MatScIE paper](https://arxiv.org/abs/2009.06819) along with instructions of usage.

## Getting Started on Ubuntu

### Getting the files

1. Download the files from [here](https://drive.google.com/file/d/1ntFN-hG3k3C0Klksn3TiFMksclYIyiMl/view?usp=sharing).
2. Unzip the files using the following command or use the GUI by clicking on the zip file.
'''sh
unzip matscie.zip -d destination_folder
'''
Remember to replace destination_folder to the actual destination folder.

### Setting up the environment

1. Make sure [miniconda](https://docs.conda.io/en/latest/miniconda.html) is installed if the application is to be installed in a virtual python environment. Else ignore the first 3 steps and move onto step 4.
2. Run the command to create a new virtual environment.
'''sh
conda create -n matscie python=3.7
'''
3. Activate the environment.
'''sh
conda activate matscie
'''
4. Move into the downloaded directory on the terminal and run the following command.
'''sh
cat requirements.txt | xargs -n 1 pip install
'''

### Running the jar file 
IMPORTANT: The jar file is essentially needed to run for the application to work. However, it has been a system with >8GB RAM is needed to run this file. See the Help section for an alternative solution.
Run the jar file using the following command.
'''sh
java -Xmx6g -jar science-parse-server-assembly-2.0.3.jar
'''

### Running the PyQT Application
Run the following command.
'''sh
python page1a.py
'''
## Usage
1. Click on the 'Browse' button and select the PDF to be processed.
2. Click on 'Add File' to add the file to the list of files. 
3. Once all the required files are added, Click on 'Run'. This may take a few minutes to process, depending on the number of files and the size of files.
4. A new window will appear with the results. Only the results of the first file in the list will be displayed.
5. Click on the appropriate radio button to see the Method, Structure, Code, Material and Parameter.
6. Click on 'Download Files' to view the results of all the files in the list in a file named 'matscie_results.txt' stored in the home directory.

## Help
1. In case the application stops executing, try to close all other applications and run again. This usually happens if the system runs out of RAM.
2. If the system RAM is <8GB, the best solution is to run the jar file in a server with more RAM. While using ssh to get access to the server, remember to forward port 8080 to the server. 
'''sh
ssh -L 8080:localhost:8080 admin@server1.example.com
'''
3. In case there are other problems while running the application, please feel free to create a new issue on this repository.

## To Do
1. Include instructions for usage in Windows and MacOS.
2. Make an executable file for the application.
