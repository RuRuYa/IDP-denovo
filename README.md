# IDP-denovo

Download and install IDP-denovo:

```make```


**For impatient people**: 

```./idpdenovo  ```

Example:

```./idpdenovo scaffold=/user/shuhua/idpdenovo/test_data/scaffold.fa lr=/user/shuhua/idpdenovo/test_data/lr.fa leftSr=/user/shuhua/idpdenovo/test_data/leftSr.fa rightSr=/user/shuhua/idpdenovo/test_data/rightSr.fa ```

For test (in directory "test_data"): "scaffold.fa", "lr.fa" "leftSr.fa" "rightSr.fa"
 
 
 
# Step 1 - SR-scaffold extension and k-mer cluster

``` scaffoldExtend ```



scaffold.fa is from Oases output (transcripts.fa), In "LR.fa", tags of sequences format are "lr1,lr2..."

```kCluster ```
        
To cluster unaligned LRs with k-mer clustering method Output includes a TXT file and a Log file
 
 
# Step 2 - Isoform annotation

 ```kCluster  kmer_size > clusterOutput 2> clusterLog ```

         
To cluster unaligned LRs with k-mer clustering method, output a TXT file and a log file to track progress of clustering
 
 
# Step 3 - Quantification

 ```MLE   python_path code_path SR_length  ```

 
Output file is "refSeq_MLE_output1.tab" to tell SR coverage for each transcript. IDP-denovo will outupt LR coverage. SR align to pseudo-reference with HISAT LR align to transcripts with GMAP
