# Understanding the deconvolution problem 

**Deconvolution** is a process of resolving something into its constituent elements or removing complication in order to clarify it or takening one state and returning it to sum of its pieces. 

Looking at deconvolution as a equation problem. The goal is to find the solution *f* of some state you wish to learn. Based on the equation:   
*f x g = h*  
where *h* = recorded signal/stat
      *g* = filter/distortion function 
      *f* -= signal/state to recover 

in terms of Spatial:  
*h* = mixture of spot expression/read counts 
*g* = unknown function comprised of expressions, and spatial location 
*f* = cell type informaiton wished to learn 

# Simple solution 
1. In each spot what is the distribution of gene counts 
2. Given a list of cell types what are the gene expressions 
