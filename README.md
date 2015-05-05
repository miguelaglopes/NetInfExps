# NetInfExps
Network inference experiments - Thesis Lopes 2015 (chapter 5)

(missing causal direction experiments - to add)

### File netinf.tar.gz
Scripts and data for the experiments described in Lopes 2015 (PhD Thesis), in particular the network inference experiments described in chapter 5.

Necessary packages: 
Pranker ( https://github.com/miguelaglopes/pranker ) and
GCnetinf ( https://github.com/miguelaglopes/GCnetinf )
which in turn require the packages: Rcpp, tseries, ppcor, randomForest and lars. R packages GeneNet, simone and g1dbn are also required. 

They consist in the inference (ie. edge ranking) of 100 networks of 50 genes in two time series datasets. 

One dataset is of yeast microarray time series, composed of 11 multiple time series. A gold standard is available, and 100 sets of 50 genes are randomly selected. These are used as the genes on which networks are inferred. 

The other dataset is of simulated GeneNetWeaver time series. It consists on 100 multiple time series of 50 genes, each with a gold standard. 

The two experiments follows the same script pattern. Each script generates a .Rdata file which is used by the next script. 

For the preparation of the datasets:    
**source("GNWdata.R")**  
**source("YEASTdata.R")**  

Generation of the networks for network inference (only on the yeast experiment). As it depends on a random generation of networks, the ouput file used in the thesis experiments is also provided ("YEASTinf-data.Rdata").  
**source("YEASTinf-data.R")**  

Scripts for network inference:  
**source("GNWinf.R")**    
**source("YEASTinf.R")**    

Network inference assessment (note: in the yeast case, a montecarlo AUPRC simulation is also provided, file "auprc.montecarlo.Rdata")  
**source("GNWassess.R")**    
**source("YEASTassess.R")**    

Each file ouputs pdf files, which are also provided
