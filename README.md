# SRA-toolkit-for-WES-and-WGS-from-Database
Baby step pipeline for installing conda. Bioconda, SRA toolkit, SRA files (WGS, WES etc.) and converting SRA files into fastq read files 
Initial steps required to install these packages in linux 

Baby step pipeline for installing conda. Bioconda, SRA toolkit, SRA files (WGS, WES etc.) and converting SRA files into fastq read files 


Step 1: Download canda in linux
1. To install conda https://bioconda.github.io/user/install.html#install-packages (Reference url)

 Open terminal
Commands:
1. curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
2. After command it ask for some yes or no and enter “y”

 conda Installation completed 

Step 2
Set up channels commands
conda config --add channels defaults
conda config --add channels bioconda
conda config --add channels conda-forge
Now Bioconda is installed

Extra packages are required for NGS analyses
Command: 
conda install bwa
conda create -n aligners bwa bowtie hisat star

Now Time to install SRA toolkit as it require conda and bioconda packages which we have installed using above commands
Command: 
conda install -c bioconda/label/cf201901 sra-tools

Now time to fetch SRA from NCBI
Command required:

prefetch
prefetch SRR18519069

Downloading may take some time and the data is stored in the folder entitled NCBI in the directory, in this case Akshay folder in the desktop is working directory


Time to convert SRA into Fastq

Go to the folder where downloaded sra file is present
open the terminal 


commnads:

fastq-dump
fasterq-dump
fasterq-dump ~/ncbi/public/sra/SRR18519069.sra --split-files --outdir .





Fastqc analyses

1.	Go the folder where fastq files are present (R1&R2)
2.	Open the linux terminal
3.	Run command: sudo  apt install fastqc (if fastqc tool is not there in the OS)
4.	Run command after installation: fastqc filename_R1 (for read 1)
5.	For read 2 : fastqc file name_R2 (for read 2)
6.	HTML and zip will be created and has fatqc results

