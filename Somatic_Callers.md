## Variant Identification
### Somatic Callers
1. **[Cake] (http://cakesomatic.sourceforge.net/)**
  * Description: standalone program, “pipeline for the integrated analysis of somatic variants in cancer genomes”; integrates four algorithms; written in Perl; required tools: samtools, tabix, vcftools, VarScan2, bambino, cmake, somaticsniper (User guide; workflow page)
  * Input: tumor and normal reads in BAM files, run through variant calling programs to generate intermediate VCF
  * Output: VCF
1. **[MuTect] (http://www.broadinstitute.org/cancer/cga/mutect)**
  * Description: Broad Institute, identification of somatic point mutations in cancer genomes; requires preprocessing of reads (GATK)
  * Input: same as GATK (FASTA reference genome, SAM read files)
  * Output: call-stats, VCF, wiggle files
1. **[Polymutt] (http://genome.sph.umich.edu/wiki/Polymutt)**
  * Description: calls SNVs and detects de novo point mutations in families
  * Input: GLF or BAM or VCF (must have identical chromosome orders)
  * Output: VCF
  <hr/>
1. **[Bassovac] (http://tvap.genome.wustl.edu/tools/bassovac/)**
  * Description: Improved Bayesian inversion somatic caller; unlike other software packages, treats effects fully probabilisticallys instead of using ad-hoc modeling; effects are integrated at the atomic level and standard probability theory integrates read tallies to the sample level and to the tumor-normal pair level; "pending public release"
  * Input:
  * Output:
1. **[CLImAT] (http://bioinformatics.ustc.edu.cn/CLImAT/)**
  * Description: standalone program; “accurate detection of copy number alteration and loss of heterozygosity in impure and aneuploid tumor samples using whole genome sequencing data”
  * Input: depth file generated by DFExtract and a config file
  * Output: .results file, .Gtype, LOG.txt, also generates visualization
1. **[DeNovoGear] (http://denovogear.sourceforge.net/)**
  * Description: de-novo variant calling and interpretation; standalone program; dependencies C++ compiler, CMake, HTSlib, Eigen, Boost
  * Input: PED and BCF
  * Output: “The output format is a single row for each putative de novo mutation (DNM), with the following fields”
1. **[EBCall] (https://github.com/friend1ws/EBCall)**
  * Description: Empirical Baysian Mutation Calling; standalone program; uses tumor/normal paired reads and non-paired normal reference samples; dependent on samtools, R and VGAM pack for R
  * Input: BAM
  * Output: not sure what exact type of file- “The format of the result is suitable for adding annotation by annovar.”
1. **[HapMuc] (https://github.com/usuyama/hapmuc)**
  * Description: standalone program; “utilizes the information of heterozygous germline variants near candidate mutations”; Dependent upon- Boost, SAMtools, BEDtools; 3 step workflow
  * Input: BAM
  * Output: BED
1. **[MultiGeMS] (https://github.com/cui-lab/multigems)**
  * Description: Multi-sample Genotype Model Selection
  * Input: .txt, pileup (SAM/BAM converted to pileup format)
  * Output: VCF
1. **[MultiSNV] (https://bitbucket.org/joseph07/multisnv/wiki/Home)**
  * Description: command-line program; calls SNVs from NGS data from multiple samples from the same patient; dependent on R, Git, cmake, Boost and compile libraries
  * Input: BAM or pileup
  * Output: VCF
1. **[MutationSeq] (http://compbio.bccrc.ca/software/mutationseq/)**
  * Description: standalone program, somatic SNV detection in tumor/normal samples; dependent on python, bamtools, boost, and LAPACK
  * Input: BAM
  * Output: VCF4.1 consisting of two parts (meta information & data lines)
1. **[qSNP] (http://www.qcmg.org/bioinformatics/tiki-index.php)**
  * Description: standalone program; SNV caller for somatic variants in “low cellularity cancer samples”
  * Input: BAM, dbSNP data, Illumina data, chrConv
  * Output: “qSNP output files are named using a 4-element pattern: <subject-id>.<snp-type>.<description>.<extension>”
1. **[RADIA] (https://github.com/aradenbaugh/radia/)**
  * Description: RNA and DNA Integrated Analysis for Somatic Mutation Detection; DNA only Method(tumor/normal pair, ignores RNA) or Triple BAM Method (uses all three datasets from same patient); dependent upon python, samtoools, pysam API, BLAT, SnpEff
  * Input: BAM
   * Reference Genome: FASTA indexed with SAMtools faidx
  * Output: VCF
1. **[RVD2] (http://genomics.wpi.edu/rvd2/)**
  * Description: sensitive, variant detection for low-depth targeted NGS data; python module or command- line program;
  * Input: tab- deliminted depth chart format (converted from pileup files)
  * Output: three hdf5 files and a vcf file
1. **[Shimmer] (https://github.com/nhansen/Shimmer)**
  * Description: standalone program; detects somatic SNVs with multiple testing correction, uses Fisher’s exact test; dependent on git, samtools, R, R statmod package; for tumor/normal matched samples
  * Input: BAM
  * Output: VCF
1. **[SNV-PPILP] (http://www.cs.helsinki.fi/en/gsa/snv-ppilp/)**
  * Description: Refines GATK’s Unified Genotyper SNV calls for “multiple samples assumed to form a phylogeny”
  * Input:
  * Output:
1. **[SomaticSniper] (http://gmt.genome.wustl.edu/packages/somatic-sniper/)**
  * Description: command-line application to identify SNPs between tumor/normal pairs- predicts probability of difference between two
  * Input: BAM
   * Reference Genome in FASTA
  * Output: VCF
1. **[Strelka] (https://sites.google.com/site/strelkasomaticvariantcaller/)**
  * Description: somatic variant calling workflow for matched tumor-normal samples; detects indels; runs on *nux-like platform
  * Input: BAM (must be sorted and indexed)- Strelka does own realignment around indels-- don’t need to do this type of pre-processing
  * Output: pair of VCF files
1. **[Triodenovo] (http://www.pitt.edu/~wec47/triodenovo.html)**
  * Description: Bayesian framework for calling de novo mutations in trios
  * Input: VCF file with PL or GL fields (recommend using GATK or samtools to generate)
  * Output: out_vcf
1. **[UNCeqr] (http://lbg.med.unc.edu/~mwilkers/unceqr_dist/)**
  * Description: finds somatic mutations using integration of DNA and RNA seq data-- boosts sensitivity for low purity tumors and rare mutations;
  * Input:”can accept a variety of sequencing inputs and configurations”
  * Output: “table of somatically mutated sites and associated information. These somatic mutations can be annotated with predicted transcript and protein effects using third party tools, such as Annovar”
1. **[Virmid] (http://sourceforge.net/projects/virmid/)**
  * Description: Virtual Microdissection for SNP calling; Java based; for disease-control matched samples; uncovers SNPs with low allele frequency by considering alpha contamination
  * Input: BAM (must be sorted and indexed- samtools sort)
  * Output: VCF and report file
