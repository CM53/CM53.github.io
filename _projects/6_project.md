---
layout: page
title: Traffic light reporter system 
description: Improving CRISPR repair rates
img: assets/img/inbre/cas9.gif
importance: 2
category: work
---

<div class="row justify-content-center">
  <div class="col-10 col-md-6 col-lg-4 mt-3 mt-md-0">
    {% include figure.liquid
       loading="eager"
       path="assets/img/inbre/cas9.gif"
       title="gif of Cas9"
       class="img-fluid rounded z-depth-1 w-75 mx-auto d-block" %}
  </div>
</div>
<div class="caption">
  a gif of CRISPR Cas9 I made when I was exploring structure/function relationship with ChimeraX as a beta tester
</div>

## Abstract  
CRISPR-Cas9 has emerged as a transformative tool for genome engineering due to its ability to generate targeted double-stranded DNA breaks (DSBs). The repair of these lesions depends on endogenous cellular pathways, as shown in **Figure 1**, primarily non-homologous end joining (NHEJ) and homology-directed repair (HDR). NHEJ is efficient but error-prone, typically resulting in loss-of-function alleles, whereas HDR enables precise sequence correction or integration of donor DNA but occurs with lower efficiency. Increasing HDR frequency is critical for therapeutic applications of CRISPR. In this work, I adapted a Traffic Light Reporter (TLR) assay to quantitatively assess HDR and NHEJ repair events in human cells. This system provides a rapid fluorescence-based approach to evaluate candidate genes identified from a non published genome-wide knockout screens that may regulate HDR. I present the design, implementation, and validation strategy for applying the TLR system to gene knockouts of interest and highlight optimization efforts to improve reproducibility of HDR measurement.  

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/inbre/inbre1.png" title="Figure 1: Schematic of Cas9-mediated DSB repair" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1. Cas9 generates targeted DSBs that are repaired by NHEJ, resulting in gene disruption, or by HDR, which restores or introduces precise sequences [6]
</div>

## Introduction  
Clustered Regularly Interspaced Short Palindromic Repeats (CRISPR) and associated Cas proteins constitute a widespread adaptive immune system in prokaryotes [1–3]. CRISPR-associated protein 9 (Cas9) has been repurposed as a programmable RNA-guided nuclease for genome engineering. Cas9 generates targeted DSBs at DNA loci complementary to the guide RNA sequence, adjacent to a protospacer-adjacent motif (PAM). Repair of these breaks relies on host-cell pathways, including NHEJ and HDR [4–6].  

NHEJ is an efficient but error-prone process, often producing indels that disrupt coding sequences [7]. HDR, in contrast, uses a donor DNA template to restore or insert precise sequences, enabling accurate gene correction [5]. While NHEJ can be exploited for loss-of-function studies, clinical applications of CRISPR require high-fidelity HDR. However, HDR occurs with lower efficiency than NHEJ, limiting its utility in therapeutic genome engineering [8].  

Recent genome-wide knockout screens in human cells have identified candidate genes that may suppress HDR. Validating these candidate regulators of repair choice is essential but labor-intensive when performed with conventional assays. To address this limitation, I adapted the Traffic Light Reporter (TLR) system [9], which enables quantitative and simultaneous measurement of HDR and NHEJ outcomes through dual fluorescent reporters. This system provides a rapid and scalable platform for testing the impact of gene knockouts on DNA repair pathway choice.  


## Methods  

### Traffic Light Reporter (TLR) Assay  
The TLR construct shown in **Figure 2** encodes a non-functional green fluorescent protein (GFP) and an out-of-frame red fluorescent protein (mCherry), both under the control of a single promoter [9]. A 38 bp insertion renders GFP inactive and shifts mCherry out-of-frame. Cas9 and a guide RNA targeting the insertion site induce a DSB. Repair by HDR restores the GFP reading frame, producing green fluorescence. Alternatively, NHEJ-induced indels may shift mCherry into frame, producing red fluorescence. Flow cytometry quantifies the proportion of GFP- and mCherry-positive cells, yielding HDR and NHEJ rates, respectively as seen in **Figure 3**.  

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/inbre/inbre2.jpg" title="Figure 2: Design of the Traffic Light Reporter (TLR)" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 2. The TLR construct contains a disrupted GFP and out-of-frame mCherry. DSB induction by Cas9 enables pathway-specific repair outcomes, visualized by GFP or mCherry fluorescence [9].
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/inbre/guide1.jpg" title="Figure 3: FACs output testing one of the Cas9 guides" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 3. Fluorescent Activated Cell Sorting (FACS) showing the count and distribution of dark cells (Q3), red cells displaying NHEJ (Q1), and green cells displaying HDR (G4), and cells showing both red and green fluorescent protein (Q2).
</div>

### Cell Culture and Transduction  
HEK293T cells were maintained under standard conditions and transduced with a lentiviral vector encoding the TLR construct. Following antibiotic selection, stable TLR reporter lines were established. For experimental assays, cells were transfected with plasmids encoding Cas9, a single-guide RNA targeting the GFP insertion, and a donor repair template as shown in **Figure 4**.  

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/inbre/inbre3.png" title="Figure 4: Workflow of TLR assay" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 4. Workflow of the TLR assay. Stable HEK293T-TLR cells are transfected with Cas9, guide RNA, and donor template. Repair outcomes are quantified by flow cytometry to determine relative HDR and NHEJ frequencies
</div>

### Gene Knockout Validation  
Candidate genes identified in the genome wide screen. Knockouts were generated by CRISPR-mediated editing and confirmed by sequencing. TLR assays were then performed in knockout and control lines to determine the effect of each gene on repair pathway choice.  

### Optimization of Assay Reproducibility  
Preliminary TLR experiments yielded variable HDR:NHEJ ratios (12 ± 7%). Optimization strategies included adjusting donor template concentrations, following previously established transfection methods [10], and testing different cell passage numbers.  

## Results and Discussion  
The TLR assay provided simultaneous and quantitative measurement of HDR and NHEJ repair in human cells. Fluorescence-based readouts enabled rapid comparison of repair pathway activity across knockout and control lines. Candidate gene knockouts conrtols which are known to promote NHEJ, were hypothesized to increase HDR frequency. Validation of additional genes from the GeCKO v2 screen will establish whether novel factors contribute to the suppression of HDR.  

Preliminary data demonstrated successful transduction of TLR constructs and generation of multiple gene knockouts. However, variability in HDR:NHEJ ratios indicated a need for protocol optimization. Refinement of transfection conditions and donor DNA concentrations is expected to stabilize the assay. Once optimized, the TLR system offers a scalable approach for systematically validating genes that regulate DNA repair pathway choice.  


## Conclusion  
I developed and implemented a Traffic Light Reporter assay to quantitatively assess DNA repair outcomes following CRISPR-Cas9 editing. This system enables high-throughput validation of candidate genes identified from genome-wide screens as regulators of HDR. Although initial experiments showed variability, optimization of assay conditions will improve reproducibility and facilitate systematic investigation of DNA repair regulation. Ultimately, this platform may contribute to strategies aimed at enhancing HDR for therapeutic genome engineering.  

## References  
1. Doudna JA, Charpentier E. The new frontier of genome engineering with CRISPR-Cas9. *Science*. 2014;346(6213).  
2. Zhang F, et al. Development and applications of CRISPR-Cas9 for genome engineering. *Cell*. 2014;157(6):1262–1278.  
3. Komor AC, Badran AH, Liu DR. CRISPR-based technologies for the manipulation of eukaryotic genomes. *Cell*. 2017;169(3):559.  
4. Lieber MR. The mechanism of double-strand DNA break repair by the nonhomologous end-joining pathway. *Annu Rev Biochem*. 2010;79:181–211.  
5. Chu VT, et al. Increasing the efficiency of homology-directed repair for CRISPR-Cas9–induced precise gene editing in mammalian cells. *Nat Biotechnol*. 2015;33:543.  
6. Wilkinson RA, et al. CRISPR RNA-guided autonomous delivery of Cas9. *Nat Struct Mol Biol*. 2019;26(1):14–24.  
7. Mao Z, et al. Comparison of nonhomologous end joining and homologous recombination in human cells. *DNA Repair*. 2008;7(10).  
8. Yin H, Kauffman KJ, Anderson DG. Delivery technologies for genome editing. *Nat Rev Drug Discov*. 2017;16:387.  
9. Certo MT, et al. Tracking genome engineering outcome at individual DNA breakpoints. *Nat Methods*. 2011;8:671.  
10. Certo MT, et al. Coupling endonucleases with DNA end–processing enzymes to drive gene disruption. *Nat Methods*. 2012;9:973.  
