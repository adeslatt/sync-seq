# sync-seq
A Nextflow workflow encapsulating the computational components to take output from the 15:1 molar libraries of gDNA:cDNA sequenced on the PacBio Revio following the protocols published in "Synchronized long-read genome, methylome, epigenome, and transcriptome for resolving a Mendelian condition".

## Citations

>Vollger MR, Korlach J, Eldred KC, Swanson E, Underwood JG, Cheng YH, Ranchalis J, Mao Y, Blue EE, Schwarze U, Munson KM, Saunders CT, Wenger AM, Allworth A, Chanprasert S, Duerden BL, Glass I, Horike-Pyne M, Kim M, Leppig KA, McLaughlin IJ, Ogawa J, Rosenthal EA, Sheppeard S, Sherman SM, Strohbehn S, Yuen AL; University of Washington Center for Mendelian Genomics (UW-CMG), Undiagnosed Diseases Network (UDN); Reh TA, Byers PH, Bamshad MJ, Hisama FM, Jarvik GP, Sancak Y, Dipple KM, Stergachis AB. Synchronized long-read genome, methylome, epigenome, and transcriptome for resolving a Mendelian condition. bioRxiv [Preprint]. 2023 Sep 27:2023.09.26.559521. doi: 10.1101/2023.09.26.559521. PMID: 37808736; PMCID: PMC10557686.

## Nextflow Processes

1. **pbsv** containerized in [pbsv-docker](https://github.com/adeslatt/pbsv-docker) using [pbsv](https://github.com/PacificBiosciences/pbsv)
2. **k-mer-variant-phasing** containerized in [k-mer-variant-phasing-docker](https://github.com/adeslatt/k-mer-variant-phasing-docker) using [k-mer-variant-phasing](https://github.com/mrvollger/k-mer-variant-phasing)
3. **HiPhase** containerzied in [hiphase-docker](https://github.com/adeslatt/hiphase-docker) using [HiPhase](https://github.com/PacificBiosciences/HiPhase)
4. **hifiasm** containerized in [hifiasm-docker](https://github.com/adeslatt/hifiasm-docker) using [hifiasm](https://github.com/chhylp123/hifiasm)
5. **yak** containerized in [yak-docker](https://github.com/adeslatt/yak-docker) using [yak](https://github.com/lh3/yak)
6. **pb-CpG-tools** containerized in [pb-CpG-tools-docker](https://github.com/adeslatt/pb-cpg-tools-docker) using [pb-CpG-tools](https://github.com/PacificBiosciences/pb-CpG-tools)
7. **pbfusion** containerized in [pbfusion-docker](https://github.com/adeslatt/pbfusion-docker) using [pbfusion](https://github.com/PacificBiosciences/pbfusion)
8. **fiberseq-fire** containerized in [fiberseq-fire-docker](https://github.com/adeslatt/fiberseq-fire-docker) using [fiberseq-fire](https://github.com/fiberseq/fiberseq-fire)


## Philosophy

My philosophy - is always an elements of style approach.  

`Input` - `process` - `output`

Containerization at each of the `process` levels, ensures modular testing.  Each of the `processes` in this workflow are made into Docker containers.  **GitHub Actions** are used to **Build Docker Images** using the default parameters from the **GitHub Workflows**.

## Disclaimer

THIS WEBSITE AND CONTENT AND ALL SITE-RELATED SERVICES, INCLUDING ANY DATA, ARE PROVIDED "AS IS," WITH ALL FAULTS, WITH NO REPRESENTATIONS OR WARRANTIES OF ANY KIND, EITHER EXPRESS OR IMPLIED, INCLUDING, BUT NOT LIMITED TO, ANY WARRANTIES OF MERCHANTABILITY, SATISFACTORY QUALITY, NON-INFRINGEMENT OR FITNESS FOR A PARTICULAR PURPOSE. YOU ASSUME TOTAL RESPONSIBILITY AND RISK FOR YOUR USE OF THIS SITE, ALL SITE-RELATED SERVICES, AND ANY THIRD PARTY WEBSITES OR APPLICATIONS. NO ORAL OR WRITTEN INFORMATION OR ADVICE SHALL CREATE A WARRANTY OF ANY KIND. ANY REFERENCES TO SPECIFIC PRODUCTS OR SERVICES ON THE WEBSITES DO NOT CONSTITUTE OR IMPLY A RECOMMENDATION OR ENDORSEMENT BY SCIENCE and TECHNOLOGY CONSULTING LLC.
