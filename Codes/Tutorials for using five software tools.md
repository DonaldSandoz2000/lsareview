Tutorials for using five software tools
===
5/16/2023

##### NOTE: This guide will demonstrate the usage of five software tools in the style of the R console. Users can access data from [here](https://github.com/labxscut/lsareview).

#### eLSA (perm and theo)

By using the Docker platform to pull images, readers can transfer data to the test file of the image for subsequent operations. The following operation takes TableS1.txt as an example.

```
docker pull panhongfei/elsa:1.0
docker start 7ba577395c39
docker exec -it 7ba577395c39 /bin/bash  
cd charade-elsa-7bed46b84456  
cd test
```
Run eLSA.
```
lsa_compute -d 3 -p perm -x 1000 -r 1 -s 50 TableS1.txt TableS1.perm.txt 
lsa_compute -d 3 -p theo -x 1000 -r 1 -s 50 TableS1.txt TableS1.theo.txt
```

```
usage: lsa_compute [-h] [-e EXTRAFILE] [-d DELAYLIMIT] [-m MINOCCUR]
                   [-p {perm,theo,mix}] [-x PRECISION]
                   [-b {0,100,200,500,1000,2000}] [-r REPNUM] [-s SPOTNUM]
                   [-t {simple,SD,Med,MAD}]
                   [-f {none,zero,linear,quadratic,cubic,slinear,nearest}]
                   [-n {percentile,percentileZ,pnz,robustZ,rnz,none}]
                   [-q {scipy}] [-T TRENDTHRESH] [-a APPROXVAR]
                   [-v PROGRESSIVE]
                   dataFile resultFile
```

#### fastLSA

Install fastLSA.

```
wget http://hallam.microbiology.ubc.ca/fastLSA/resources/fastLSALinux.tar.gz
tar xvzf fastLSALinux.tar.gz
cd fastLSALinux
g++ fastLSA.cpp pnorm.cpp lsaPack.cpp thread.cpp lsaParse.cpp -o fastLSA -pthread
```
Run fastLSA, using TableS1.txt as an example.
```
./fastLSA -i TableS1.txt -o TableS1fastout.txt -d 3 -m 0.2 -a 0.0001 -r 1000000 -t 2
```
```
Usage: ./fastLSA [-i  inputfile] [-o  outputfile] 
                 [-d  maximum time lag] 
                 [-m  minimum LSA value][-a  alpha] 
                 [-r  distribution resolution]
                 [-t  number of threads]
```

#### DDLSA

Readers can click [here](https://github.com/BlueStamford/DDLSA) to download the DDLSA code.

```
source("F:\\DDLSA-master\\DDLSA\\R\\LocalScore.R")
source("F:\\DDLSA-master\\DDLSA\\R\\DataDrivenLSA.R")

setwd("D:/table S1-S10")
temp=list.files(path="D:/table S1-S10",pattern="*.txt")
for(k in 1:length(temp)){
  start<-Sys.time()
  file=read.table(temp[k],row.names = 1)
  file <- as.matrix(file) 
  file <- t(apply(file, 1, function(x) x / apply(file, 2, sum)))
  otu1<-c()
  otu2<-c()
  pvalue<-c()
for (i in 1:(nrow(file)-1)){
  for (r in (i+1):nrow(file)){
    g1=rownames(file)[i]
    g2=rownames(file)[r]
    p <- DataDrivenLSA(file [i,],file[r,], 3)[2] 
    otu1=c(otu1,g1)
    otu2=c(otu2,g2)
    pvalue=c(pvalue,p)
    } 
  } 
q<-p.adjust(pvalue,method = "BH")
  data_cor<-data.frame(otu1,otu2,pvalue,q)
  setwd("D:/table S1-S10/DDLSAresult")
  write.table(data_cor,temp[k],quote=F,row.names = F,sep='\t')
  end<-Sys.time()
  runningtime<-end-start
  print(temp[k],cat(runningtime),sep='\t')
  setwd("D:/table S1-S10") 
}

```

#### MBBLSA

Readers can click [here]( https://github.com/BlueStamford/MBBLSA) to download the MBBLSA code.
```
source("F:\\MBBLSA-master\\MBBLSA\\R\\LocalScore.R")
source("F:\\MBBLSA-master\\MBBLSA\\R\\MBBLSA.R")
setwd("D:/table S1-S10")
temp=list.files(path="D:/table S1-S10",pattern="*.txt")
for(k in 1:length(temp)){
  start<-Sys.time()
  file=read.table(temp[k],row.names = 1)
  file <- as.matrix(file) 
  otu1<-c()
  otu2<-c()
  pvalue<-c() 
  for (i in 1:(nrow(file)-1)){
    for (r in (i+1):nrow(file)){
      g1=rownames(file)[i]
      g2=rownames(file)[r]
      p=MovingBlockBootstrap(file[i,],file[r,],maxDelay = 3)[2]
      otu1=c(otu1,g1)
      otu2=c(otu2,g2)
      pvalue=c(pvalue,p)
    }
  }
   
  q<-p.adjust(pvalue,method = "BH")
  
  data_cor<-data.frame(otu1,otu2,pvalue,q)
  setwd("D:/table S1-S10/MBBLSAresult")
  write.table(data_cor,temp[k],quote=F,row.names = F,sep='\t')
  end<-Sys.time()
  runningtime<-end-start
  print(temp[k],cat(runningtime),sep='\t')
  setwd("D:/table S1-S10")
  
}
```





