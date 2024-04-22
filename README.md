# WGS_anaylsis_workflow

The repository contains the analysis workflow used to analyze whole-genome sequencing datasets generated during this study: [**<em>add publication DOI here</em>**].
The workflow is based around several tools that have been incorporated into 3 Snakemake pipelines (Fig. 1).

The aim of the first pipeline (**Snakefile_GATK**) is to generated an alignment file (<code>{sample}/{sample}_WGS_hg19_recalibrated.sorted.bam</code>) and two normalized variant call files (VCFs), generated by <code>HaplotypeCaller</code> and <code>DeepVariant</code>, respectively.

The second pipeline (**Snakefile_SV_pipeline**) produces strctural variant calls using six different base tools (<code>Lumpy</code>, <code>Manta</code>, <code>GRIDSS</code>, <code>WHAMg</code>, <code>CNVpytor</code>, and <code>Delly2</code>), which are finally merged into a single VCF file (Fig. 2).

The third pipeline (**Snakefile_Nirvana**) integrates Nirvana to annotate all variants and finally merges and filters the annotated variants based on a genes list of interest (Fig. 1).
