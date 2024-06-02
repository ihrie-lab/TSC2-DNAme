Human TSC2 Mutant Cells Exhibit Aberrations in Early Neurodevelopment Accompanied by Changes in the DNA Methylome

This is the whole genome bisulfite sequencing workflow used in "Human TSC2 Mutant Cells Exhibit Aberrations in Early Neurodevelopment Accompanied by Changes in the DNA Methylome."

After sequencing, intial pre-processing was performed. 
    1. Raw files were first trimmed using Trim-Galore in the trimming.slrm script
    2. Trimmed files were then mapped to hg38A genome using Abismal in the abismal.slrm script (run abismal_index.slrm first)
    3. Mapped files were then processed through Methpipe package from Smith Lab is the methprocess.slrm script

Once HMRs (Hypomethylated regions) have been called, the roimethstat.slrm script was run which gives statistics on DNA methylation levels. 

DMRs (differentially methylated regions) were then calculated using dmr_calc_iPSCmerge.slrm, dmr_calc_mergetime.slrm, dmr_calc_NPCmerge.slrm script depending on samples of interest.

HMRs and DMRs were then intersected using the intersect.slrm script. Intersected HMRs and DMRs are then processed by the intersectDMRHMR.Rmd script that annotates the intersected regions and gives percentage of HMRs that include DMRs.

