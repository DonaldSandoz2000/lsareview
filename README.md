Algorithms for identifying local associations in biological time series
===

### INTRODUCTION

We conducted a basic comparison among five available open-source LSA software tools (including eLSA, fastLSA, LocSim, MBBLSA, and DDLSA, which implemented permutation or theoretical methods to estimate the statistical significance of LS scores) and LTA software tools, as presented in **Table 1**. For eLSA, in addition to local similarity analysis, it also includes other functions such as trend series analysis and bootstrap confidence intervals.In addition, **Table 2** presented a summary of the real applications of these LSA and LTA software tools in various data domains and specialties, aiming to provide practitioners with a convenient overview of the wide adoption of these tools. Additionally, for the selection of appropriate software tools tailored to distinct tasks or datasets, please refer to **Figure 1**.

**Table 1.** Feature comparison of LSA analysis software tools.
<style>
  .custom-table {
    width: 80%; /* 表格宽度 */
    border-collapse: collapse;
  }
  .custom-table th, .custom-table td {
    padding: 10px;
    border: 1px solid black;
    text-align: center; /* 文字居中对齐 */
  }
  .col-width-12 {
    width: 12.5%; /* 自定义列宽度 */
  }
  .table-caption {
    text-align: left; /* 将表格标题左对齐 */
  }
</style>

<table class="custom-table">
  <tr style="line-height: 0.99;">
    <th class="col-width-12">Method<br>(Software)</th>
    <th class="col-width-12">LSA<br>(LocSim)</th>
    <th class="col-width-12">LSA<br>(eLSA)</th>
    <th class="col-width-12">LSA<br>(fastLSA)</th>
    <th class="col-width-12">LSA<br>(MBBLSA)</th>
    <th class="col-width-12">LSA<br>(DDLSA)</th>
    <th class="col-width-12">LTA<br>(eLSA)</th>
    <th class="col-width-12">LTA<br>(TC_linkage_infer)</th>
  </tr>
  <tr style="line-height: 0.99;">
    <td>Reference</td>
    <td>Ruan et al.<br>2006<br>[1]</td>
    <td>Xia et al.<br>2011, 2013<br>[2, 3]</td>
    <td>Durno et al.<br>2013<br>[4]</td>
    <td>Zhang et al.<br>2018<br>[5]</td>
    <td>Zhang et al.<br>2019<br>[6]</td>
    <td>Xia et al.<br>2011, 2013<br>[2, 3]</td>
    <td>He et al.<br>2006<br>[7]</td>
  </tr>
  <tr style="line-height: 0.99;">
    <td>Homepage</td>
    <td><a href="https://www-rcf.usc.edu/~fsun/Programs/local_similarity/lsaMain.html">Link</a></td>
    <td><a href="https://github.com/labxscut/elsa">Link</a></td>
    <td><a href="http://www.cmde.science.ubc.ca/hallam/fastLSA">Link</a></td>
    <td><a href="https://github.com/BlueStamford/MBBLSA">Link</a></td>
    <td><a href="https://github.com/BlueStamford/DDLSA">Link</a></td>
    <td><a href="https://github.com/labxscut/elsa">Link</a></td>
    <td><a href="http://www.gbf.de/SystemsBiology">Link</a></td>
  </tr>
  <tr style="line-height: 0.99;">
    <td>Language</td>
    <td>R</td>
    <td>Python and C++</td>
    <td>C++</td>
    <td>R</td>
    <td>R</td>
    <td>Python and C++</td>
    <td>-</td>
  </tr>
  <tr style="line-height: 0.99;">
    <td>Replicated Data</td>
    <td>No</td>
    <td>Yes</td>
    <td>No</td>
    <td>Yes</td>
    <td>Yes</td>
    <td>Yes</td>
    <td>Yes</td>
  </tr>
  <tr style="line-height: 0.99;">
    <td>Confidence Interval</td>
    <td>No</td>
    <td>Yes</td>
    <td>No</td>
    <td>No</td>
    <td>No</td>
    <td>Yes</td>
    <td>No</td>
  </tr>
  <tr style="line-height: 0.99;">
    <td>p-value</td>
    <td>Permutation</td>
    <td>Theory and Permutation</td>
    <td>Theory</td>
    <td>Permutation</td>
    <td>Theory</td>
    <td>Theory and Permutation</td>
    <td>Permutation</td>
  </tr>
</table>
</center>

note：The software tools fastLSA and TC_linkage_infer have been discontinued.

**Table 2.** Example real applications of LSA and LTA methods and software tools.

<style>
  .custom-table {
    width: 100%; /* 表格宽度 */
    border-collapse: collapse;
  }
  .custom-table th, .custom-table td {
    padding: 10px;
    border: 1px solid black;
    text-align: center; /* 文字居中对齐 */
  }
  .col-width-12 {
    width: 12.5%; /* 自定义列宽度 */
  }
  .table-caption {
    text-align: left; /* 将表格标题左对齐 */
  }
</style>

<table class="custom-table">
  <tr>
    <th>Method (Software)</th>
    <th>Domain</th>
    <th>Data Source</th>
    <th>Example Applications</th>
  </tr>
  <tr>
    <td rowspan="7">LSA (eLSA)</td>
    <td rowspan="2">Health Science</td>
    <td>16S rRNA Seq</td>
    <td>Refs. [8-12]</td>
  </tr>
  <tr>
    <td>Metagenomics</td>
    <td>Ref. [13]</td>
  </tr>
  <tr>
    <td>Food / Agriculture</td>
    <td>16S rRNA Seq</td>
    <td>Refs. [14-18]</td>
  </tr>
  <tr>
    <td rowspan="3">Ecology</td>
    <td>Metagenomics</td>
    <td>Refs. [19-21]</td>
  </tr>
  <tr>
    <td>RNA-Seq</td>
    <td>Ref. [22]</td>
  </tr>
  <tr>
    <td>16S rRNA Seq</td>
    <td>Refs. [23-34]</td>
  </tr>
  <tr>
    <td>Bioenergy</td>
    <td>16S rRNA Seq</td>
    <td>Refs. [35,36]</td>
  </tr>
  <tr>
    <td>LSA (fastLSA)</td>
    <td>Ecology</td>
    <td>16S rRNA Seq</td>
    <td>Refs. [37-41]</td>
  </tr>
  <tr>
    <td rowspan="7">LTA</td>
    <td>Molecular systems biology</td>
    <td>RNA-Seq</td>
    <td>Refs. [42, 43]</td>
  </tr>
  <tr>
    <td>Biomedicine</td>
    <td>RNA-Seq</td>
    <td>Ref. [44]</td>
  </tr>
</table>


<img src="Figure%201.png" alt="Figure 1" style="max-width: 80%; height: auto;">

**Figure 1.** Local similarity analysis software tool choice decision tree.

### DOCUMENT
This software package stores the code for generating benchmark datasets and the usage methods of five software for calculating biological time series correlations. Contains the following two folders.

**Codes**--Contains five software usage methods `Tutorials for using five software tools. md` and Lotka Volterra dataset generation code `lotka Volterra. ipynb`. The generation code for the dataset comes from Weiss et al.(Correlation detection strategies in microbial data sets vary widely in sensitivity and precision，2016), and if readers want to learn about the generation of other model datasets, they can click [here](ftp.microbio.me/pub/cooccurrence_files.zip) to obtain it.

**Tables S1-S10**--The input data of five software tools was obtained by deleting a sequence with zero values exceeding 80% from the table set 2.6-2.15 generated by `lotka-volterra.ipynb`, resulting in Tables S1-S10.

### USAGE

1. Generate benchmark datasets Tables Set 2.6-2.15 using `lotka-volterra.ipynb`;
2. We pre-processed the benchmark datasets and filtered out sequences with more than 80% of zero values in one sequence,resulting in Tables S1-S10；
3. Use `Tutorials for using five software tools.md` to input Tables S1-S10 into five software tools to obtain the output results and runtime.

### REFERENCES


1.	Ruan Q, Dutta D, Schwalbach MS et al. Local similarity analysis reveals unique associations among marine bacterioplankton species and environmental factors. Bioinformatics 2006;22:2532-8.
2.	Xia LC, Steele JA, Cram JA et al. Extended local similarity analysis (eLSA) of microbial community and other time series data with replicates. BMC Syst Biol 2011;5:S15.
3.	Xia LC, Ai D, Cram J et al. Efficient statistical significance approximation for local similarity analysis of high-throughput time series data. Bioinformatics 2013;29:230-7.
4.	Durno WE, Hanson NW, Konwar KM et al. Expanding the boundaries of local similarity analysis. BMC Genomics 2013;14 Suppl 1:S3.
5.	Zhang F, Shan A and Luan Y. A novel method to accurately calculate statistical significance of local similarity analysis for high-throughput time series. Stat Appl Genet Mol Biol 2018;17:20180019.
6.	Zhang F, Sun F, Luan Y. Statistical significance approximation for local similarity analysis of dependent time series data. BMC Bioinformatics 2019;20:53.
7.	He F, Zeng AP. In search of functional association from time-series microarray data based on the change trend and level of gene expression. BMC Bioinformatics 2006;7:69.
8.	Seekatz AM, Panda A, Rasko DA et al. Differential Response of the Cynomolgus Macaque Gut Microbiota to Shigella Infection. PLoS ONE 2013;8:e64212.
9.	Sun J, Liao XP, D'Souza AW et al. Environmental remodeling of human gut microbiota and antibiotic resistome in livestock farms. Nat Commun 2020;11:1427.
10.	Zheng W, Huyan J, Tian Z et al. Clinical class 1 integron-integrase gene - A promising indicator to monitor the abundance and elimination of antibiotic resistance genes in an urban wastewater treatment plant. Environ Int 2020;135:105372.
11.	Copeland E, Leonard K, Carney R et al. Chronic Rhinosinusitis: Potential Role of Microbial Dysbiosis and Recommendations for Sampling Sites. Front Cell Infect Microbio 2018;8:57.
12.	Džunková M, Martinez-Martinez D, Gardlík R et al. Oxidative stress in the oral cavity is driven by individual-specific bacterial communities. NPJ Biofilms Microbiomes 2018;4:29.
13.	Xu J, Wang H, Xu R et al. The diurnal fluctuation of colonic antibiotic resistome is correlated with nutrient substrates in a pig model. Sci Total Environ 2023;891:164692.
14.	Jiang CL, Jin WZ, Tao XH et al. Black soldier fly larvae (Hermetia illucens) strengthen the metabolic function of food waste biodegradation by gut microbiome. Microb Biotechnol 2019;12:528-543.
15.	Shade A, McManus PS, Handelsman J. Unexpected diversity during community succession in the apple flower microbiome. mBio 2013;4:e00602-12.
16.	Wang H, Sangwan N, Li HY et al. The antibiotic resistome of swine manure is significantly altered by association with the Musca domestica larvae gut microbiome. ISME J 2017;11:100-111.
17.	Simons AL, Churches N, Nuzhdin S. High turnover of faecal microbiome from algal feedstock experimental manipulations in the Pacific oyster (Crassostrea gigas). Microb Biotechnol 2018;11:848-858.
18.	Garcia J, Gannett M, Wei L et al. Selection pressure on the rhizosphere microbiome can alter nitrogen use efficiency and seed yield in Brassica rapa. Commun Biol 2022;5:959.
19.	Wang Y, Ye J, Ju F et al. Successional dynamics and alternative stable states in a saline activated sludge microbial community over 9 years. Microbiome 2021;9:199.
20.	Roux S, Chan LK, Egan R et al. Ecogenomics of virophages and their giant virus hosts assessed through time series metagenomics. Nat Commun 2017;8:858.
21.	Ki BM, Ryu HW, Cho KS. Extended local similarity analysis (eLSA) reveals unique associations between bacterial community structure and odor emission during pig carcasses decomposition. J Environ Sci Health A Tox Hazard Subst Environ Eng 2018;53:718-727.
22.	Thiriet-Rupert S, Carrier G, Trottier C et al.Identification of transcription factors involved in the phenotype of a domesticated oleaginous microalgae strain of Tisochrysis lutea.Algal Research 2018;30:59-72.
23.	Needham DM, Sachdeva R, Fuhrman JA. Ecological dynamics and co-occurrence among marine phytoplankton, bacteria and myoviruses shows microdiversity matters. ISME J 2017;11:1614-1629.
24.	Pollet T, Berdjeb L, Garnier C et al. Prokaryotic community successions and interactions in marine biofilms: the key role of Flavobacteriia. FEMS Microbiol Ecol 2018;94.
25.	Chow CE, Sachdeva R, Cram JA et al. Temporal variability and coherence of euphotic zone bacterial communities over a decade in the Southern California Bight. ISME J 2013;7:2259-73.
26.	Ju F, Zhang T. Bacterial assembly and temporal dynamics in activated sludge of a full-scale municipal wastewater treatment plant. ISME J 2015;9:683-95.
27.	Kankan Z,Haodan Y,Ran X et al. The only constant is change: Endogenous circadian rhythms of soil microbial activities.Soil Biol Biochem. 2022;173:108805.
28.	Lee YY, Seo Y, Ha M et al. Evaluation of rhizoremediation and methane emission in diesel-contaminated soil cultivated with tall fescue (Festuca arundinacea). Environmental Research 2021;194:110606.
29.	Thomas F, Cébron A. Short-Term Rhizosphere Effect on Available Carbon Sources, Phenanthrene Degradation, and Active Microbiome in an Aged-Contaminated Industrial Soil. Front Microbiol 2016;7:92.
30.	Lee YY, Lee SY, Cho KS. Phytoremediation and bacterial community dynamics of diesel-and heavy metal-contaminated soil: Long-term monitoring on a pilot scale. International Biodeterioration & Biodegradation 2023;183:105642.
31.	Lee YY, Choi H, Cho KS. Effects of carbon source, C/N ratio, nitrate, temperature, and pH on N2O emission and functional denitrifying genes during heterotrophic denitrification. J Environ Sci Health A Tox Hazard Subst Environ Eng 2019;54:16-29.
32.	Fletcher-Hoppe C, Yeh YC, Raut, Y et al. Symbiotic UCYN-A strains co-occurred with El Niño, relaxed upwelling, and varied eukaryotes over 10 years off Southern California. ISME COMMUN 2023;3:63.
33.	Kwon JH, Park HJ, Lee YY et al. Evaluation of denitrification performance and bacterial community of a sequencing batch reactor under intermittent aeration. J Environ Sci Health A Tox Hazard Subst Environ Eng 2020;55:179-192.
34.	Carini P, Delgado-Baquerizo M, Hinckley ES et al. Effects of Spatial Variability and Relic DNA Removal on the Detection of Temporal Dynamics in Soil Microbial Communities. mBio 2020;11:e02776-19.
35.	Kim TG, Yun J, Cho KS. The close relation between Lactococcus and Methanosaeta is a keystone for stable methane production from molasses wastewater in a UASB reactor. Appl Microbiol Biotechnol 2015;99:8271-83.
36.	Lee YY, Kim TG, Cho KS. Effects of proton exchange membrane on the performance and microbial community composition of air-cathode microbial fuel cells. J Biotechnol 2015;211:130-7.
37.	Steffen K, Indraningra, AAG, Erngren I et al. Oceanographic setting influences the prokaryotic community and metabolome in deep-sea sponges. Sci Rep 2022;12:3356.
38.	Jang J, Park J, Hwang CY et al. Abundance and diversity of antibiotic resistance genes and bacterial communities in the western Pacific and Southern Oceans. Sci Total Environ 2022;822:153360.
39.	Zhuang Y, Chai J, Cui K et al. Longitudinal Investigation of the Gut Microbiota in Goat Kids from Birth to Postweaning. Microorganisms 2020;8:1111.
40.	Bergk Pinto B, Maccario L, Dommergue A et al. Do Organic Substrates Drive Microbial Community Interactions in Arctic Snow? Front Microbiol 2019;10:2492.
41.	Auladell A, Sánchez P, Sánchez O et al. Long-term seasonal and interannual variability of marine aerobic anoxygenic photoheterotrophic bacteria. ISME J 2019;13:1975-87.
42.	He F, Chen H, Probst-Kepper M et al. PLAU inferred from a correlation network is critical for suppressor function of regulatory T cells. Mol Syst Biol 2012;8:624.
43.	Gonçalves PJ,Aires SR,Francisco PA et al. Regulatory Snapshots: integrative mining of regulatory modules from expression time series and regulatory networks. PLoS ONE 2017;7:e35977.
44.	Sudhakar P, Reck M, Wang W et al. Construction and verification of the transcriptional regulatory response network of Streptococcus mutans upon treatment with the biofilm inhibitor carolacton. BMC Genomics 2014;15:362.


