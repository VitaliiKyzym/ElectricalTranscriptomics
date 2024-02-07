# Investigating Transcriptomics Data in Electrically Stimulated Cardiomyocytes

The main purpose of the project was to perform an extensive gene expression analysis using microarray data obtained from cardiomyocytes subjected to electrical stimulation. The microarray data used in the analysis was taken from the paper ["Electrical signals affect the cardiomyocyte transcriptome independently of contraction"](https://cris.maastrichtuniversity.nl/en/publications/electrical-signals-affect-the-cardiomyocyte-transcriptome-indepen). In this study, the researchers stimulated cardiac cells with and without blebbistatin (an inhibitor of contraction). Using R with the limma package, multiple microarray replicates were processed to perform Differential Gene Expression Analysis (DGEA) which provided insights into gene expression features such as the magnitude of change (log Fold Change) and the certainty (P-value) of the analysis. The following DGE table was then used in Cytoscape to visually represent the protein interactions among the upregulated and downregulated gene sets. This approach facilitated the identification of gene hubs that may be associated with the influence of electrical stimulation on cardiomyocyte function. Lastly, enrichment analysis was performed to investigate whole-pathway effect of the electrical stimulation which aimed to uncover broader insights into how electrical stimulation impacts various biological pathways within cardiomyocytes. Thus, the project aimed to push the transcriptomic investigation of the old paper by perfoming an analysis on DGE, network analysis as well as an Enrichment Analysis. In summary, this project sought to advance the transcriptomic investigation initiated by the aforementioned paper by conducting comprehensive analyses on DGE, network interactions, and enrichment pathways. Through these analyses, a deeper understanding of the effects of electrical stimulation on cardiomyocyte gene expression and function was pursued.

## Installing and Executing

1. Uncompress the two zip files in the repository which contain the raw microarray reads

2. Still in progress

## Results and Visualizations

Limma (linear models and differential expression for microarray data) in R was used to perform Differential Gene Expression Analysis on the microarray data present in the initial paper. Three replicates were used for each condition and a custom python script was used to obtain the design matrix and expression file that was used as input for limma's empirical Bayes function. The graph below illustrates the DGEA in the form of a volcano plot and a mean difference plot. As shown below, there is a large difference in gene expression between the stimulated and unstimulated cardiomyocytes.

![Image Alt text](/figs/volcano-md-plot.png)

A key method of analyzing the DGEA results is Network Analysis which explores protein-protein interactions within a gene set. Using Cytoscape, the genes with the largest log Fold Change (logFC) were converted to their respective proteni names and simulated as a network of interacting proteins. The analysis showed key hubs in the network that might regulate the cardiomyocytes response to electrical stimulation. Shown below is a figure of the network for one condition.

![Image Alt text](/figs/network-analysis.png)

While Network Analysis only shows the interactions of the genes between themselves, an Enrichment Analysis can help uncover the bigger picture. Specifically, it calculates which pathways are overexpressed when certain gene expression changes occur. Using GSEAPY in Python and a number of  enrichment analysis databases, the figure below was generated showing which cellular proccess are activated in cardiomyocytes when electrically stimulated.

![Image Alt text](/figs/enrichment-analysis.png)


