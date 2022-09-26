# pySCENIC_implementation

Make sure the below files are saved in resources folder

hs_hgnc_tfs.txt 

hg38__refseq-r80__10kb_up_and_down_tss.mc9nr.feather

motifs-v9-nr.hgnc-m0.001-o0.0.tbl

hg38__refseq-r80__500bp_up_and_100bp_down_tss.mc9nr.feather


```
mkdir results
```


expression_matrix.csv.gz: gene expression matrix in .csv.gz

tf_list: Transcription factor list in .txt

output_ADJ.tsv: output file to save grnboost results in .tsv


```
arboreto_with_multiprocessing.py expression_matrix.csv.gz resources/hs_hgnc_tfs.txt --method grnboost2 --output output_ADJ.tsv --num_workers 30 --seed 777
```


```
pyscenic ctx output_ADJ_tsv resources/hg38__refseq-r80__10kb_up_and_down_tss.mc9nr.feather resources/hg38__refseq-r80__500bp_up_and_100bp_down_tss.mc9nr.feather --annotations_fname resources/motifs-v9-nr.hgnc-m0.001-o0.0.tbl --expression_mtx_fname expression_matrix.csv.gz --output output_ADJ.tsv --mask_dropouts --num_workers 30
```

