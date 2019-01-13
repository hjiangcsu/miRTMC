Introduction

miRTMC is noval miRNA target prediction method based on matrix completion algorithm.It is used for predicting miRNA targets by integrating miRNA seed sequence simlarity, 3'UTR sequence similarity and the validated miRNA targets. The command-line verdion of miRTMC can be run on a Windows or Linux (ubuntu 16.04 recommended) platform. Here, we provide software packages and the datasets for download.

1.Software
(1) Linux platform:   
    miRTMC_linux: the miRTMC program running on Linux; 
    para.txt:  the parameters configuration file for miRTMC_linux
(2) Windows platform: 
    miRTMC_windows.exe: the miRTMC program running on Windows
    para.txt:  the parameters configuration file for miRTMC_Windows

The description of para.txt:

gene similarity:	the file name of gene similarity matrix file.
miRNA similarity:	the file name of miRNA similarity matrix file
miRNA gene interaction:	the file name of miRNA-gene interaction matrix file, row: genes, column: miRNAs
alpha:	the parameter of ADMM-R4SVD (see the paper for details)
lambda:	the parameter of ADMM-R4SVD (see the paper for details)
gama:	the parameter of ADMM-R4SVD, learning rate.
tol:	tolerance
maxiter:        the max iteration of the second step of ADMM-R4SVD.
maxiter_fk:	the max iteration of the first step of ADMM-R4SVD.

The computational result of this program depend on the random numbers generated, which may not be exactely the same as those shown in the manuscript submitted to Bioinformatics.
____________________________________________________________________________________________________________________________________________

For Windows platform
The source code of miRTMC is compiled by MATLAB 2016b (64-bit version). Before you run this program on your computer, verify the MATLAB Runtime version 9.1 (R2016b) is installed.

You can download MATLAB Runtime version 9.1 (R2016b) from the MathWorks Web site:   http://www.mathworks.com/products/compiler/mcr/index.html

Step 1. Install MATLAB Runtime version 9.1 (R2016) (if your computer has MATLAB 2016b installed, ignore this step)
(1) Run MCR_R2016_win64_installer.exe;
(2) Add the installation Path of MCRInstaller to windows system environment variable

Step 2. Run program miRTMC
(1) Open a Dos command prompt shell window;
(2) Change the directory to the fold that including miRTMC_windows.exe and dataset files.
(3) Enter command: miRTMC_windows.exe

After running miRTMC_windows.exe, the result file Result_MTmatrix.txt is generated. This result file is the completed miRNA-gene interaction matrix file containing predicted scores for unknown miRNA-gene interactions.  

______________________________________________________________________________________________________________________________________________

For Linux platform
The source code of miRTMC is compiled by MATLAB 2016b (64-bit version). Before you run this program on your computer, verify the MATLAB Runtime version 9.1 (R2016b) is installed.

You can download MATLAB Runtime version 9.1 (R2016b) from the MathWorks Web site:   http://www.mathworks.com/products/compiler/mcr/index.html

Step 1. Install MATLAB Runtime version 9.1 (R2016) for Linux
(1) create a tmp fold for unzip the file MCR_R2016b_glnxa64_installer.zip by using the following command:
      mkdir tmp
      mv MCR_R2016b_glnxa64_installer.zip ./tmp 
      cd ./tmp
      unzip MCR_R2016b_glnxa64_installer.zip -d MCRInstaller 

(2) install by using following command:
      cd MCRInstaller
      ./install -mode silent -agreeToLicense  yes

(3) add the system environment variable:
     vi /etc/profile 

# add new environmental variables to /etc/profile     
export PATH=/usr/local/MATLAB/R2016b/bin:$PATH


export MCR_HOME=/usr/local/MATLAB/MATLAB_Runtime
export LD_LIBRARY_PATH=$MCR_HOME/v91/runtime/glnxa64:$MCR_HOME/v91/bin/glnxa64:$MCR_HOME/v91/sys/java/jre/glnxa64/jre/lib/amd64/server:$MCR_HOME/v91/sys/os/glnxa64:$MCR_HOME/v91/sys/java/jre/glnxa64/jre/lib/amd64:$MCR_HOME/v91/sys/java/jre/glnxa64/jre/lib/amd64/native_threads
export XAPPLRESDIR=$MCR_HOME/v91/X11/app-defaults

    source /etc/profile # # reload /etc/profile

Step 2. Run program miRTMC_linux
(1) Open a terminal;
(2) Change the directory to the fold that including miRTMC_linux and dataset files.
(3) Enter command: ./miRTMC   

After running miRTMC_linux,the result file Result_MTmatrix.txt is generated. This result file is the completed miRNA-gene interaction matrix file containing predicted scores for unknown miRNA-gene interactions.  
                        
