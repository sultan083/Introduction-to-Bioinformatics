In this tutorial, we will learn how to do RNA-seq analysis using HISAT, StringTie and Ballgown, using a protocol published in the following paper at Nature Protocol. 


Transcript-level expression analysis of RNA-seq experiments with HISAT, StringTie and Ballgown.

#1. Setup and virtual machine with Centos 6.5 system at the USTC cloud service.

#2. Software installation.

Open an account at USTC cloud service, and set up a virtual machine as a server:

http://cloud.ustc.edu.cn/

Connect to the virtual machine. Using Xshell

Software installation:

```ruby
abc

```

```linux
mkdir $HOME/bin
export PATH=$HOME/bin:$PATH
sudo yum groupinstall 'Development Tools'
cd ~
mkdir tools
cd tools
```

```linux
wget http://staff.ustc.edu.cn/~sma/bioinfo_tools/samtools-bcftools-htslib-1.0_x64-linux.tar.bz2
tar –xjf samtools-bcftools-htslib-1.0_x64-linux.tar.bz2
cp samtools-bcftools-htslib-1.0_x64-linux/bin/samtools ~/bin

wget ftp://ftp.ccb.jhu.edu/pub/infphilo/hisat2/downloads/hisat2-2.0.4-Linux_x86_64.zip
unzip hisat2-2.0.4-Linux_x86_64.zip
cp hisat2-2.0.4/hisat2* ~/bin
cp hisat2-2.0.4/*py ~/bin

wget http://ccb.jhu.edu/software/stringtie/dl/stringtie-1.3.0.Linux_x86_64.tar.gz
tar xvfz stringtie-1.3.0.Linux_x86_64.tar.gz
cp stringtie-1.3.0.Linux_x86_64/stringtie ~/bin
```
```linux
sudo yum install openssl-devel
sudo yum install libcurl-devel
sudo yum install httr
sudo yum install libxml2-devel
sudo yum install screen
```

Intall R packages

```linux
sudo R
```

```R
install.packages("devtools",repos="http://cran.us.r-project.org")
source("http://www.bioconductor.org/biocLite.R")
biocLite(c("alyssafrazee/RSkittleBrewer","ballgown", "genefilter","dplyr","devtools"))
q()
```

Download and unzip the data

```linux
screen
cd ~
mkdir my_rnaseq_exp
cd my_rnaseq_exp
wget ftp://ftp.ccb.jhu.edu/pub/RNAseq_protocol/chrX_data.tar.gz
tar xvzf chrX_data.tar.gz
```





3. Download the data files.

4. Analysis
