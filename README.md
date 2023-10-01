Algorithms for identifying local associations in biological time series
===

### INTRODUCTION

We conducted a basic comparison among five available open-source LSA software tools (including eLSA, fastLSA, LocSim, MBBLSA, and DDLSA, which implemented permutation or theoretical methods to estimate the statistical significance of LS scores) and LTA software tools, as presented in **Table 1**. For eLSA, in addition to local similarity analysis, it also includes other functions such as trend series analysis and bootstrap confidence intervals.In addition, **Table 2** presented a summary of the real applications of these LSA and LTA software tools in various data domains and specialties, aiming to provide practitioners with a convenient overview of the wide adoption of these tools. Additionally, for the selection of appropriate software tools tailored to distinct tasks or datasets, please refer to **Figure 1**.

**Table 1.** Feature comparison of LSA analysis software tools.

<table class="custom-table">
  <tr>
    <th class="col-width-12">Method<br>(Software)</th>
    <th class="col-width-12">LSA<br>(LocSim)</th>
    <th class="col-width-12">LSA<br>(eLSA)</th>
    <th class="col-width-12">LSA<br>(fastLSA)</th>
    <th class="col-width-12">LSA<br>(MBBLSA)</th>
    <th class="col-width-12">LSA<br>(DDLSA)</th>
    <th class="col-width-12">LTA<br>(eLSA)</th>
    <th class="col-width-12">LTA<br>(TC_linkage_infer)</th>
  </tr>
  <tr>
    <td>Reference</td>
    <td>Ruan et al.<br>2006<br>[1]</td>
    <td>Xia et al.<br>2011, 2013<br>[2, 3]</td>
    <td>Durno et al.<nobr><br>2013<br>[4]</td>
    <td>Zhang et al.<br>2018<br>[5]</td>
    <td>Zhang et al.<br>2019<br>[6]</td>
    <td>Xia et al.<br>2011, 2013<br>[2, 3]</td>
    <td>He et al.<br>2006<br>[7]</td>
  </tr>
  <tr>
    <td>Homepage</td>
    <td><a href="https://www-rcf.usc.edu/~fsun/Programs/local_similarity/lsaMain.html">Link</a></td>
    <td><a href="https://github.com/labxscut/elsa">Link</a></td>
    <td><a href="http://www.cmde.science.ubc.ca/hallam/fastLSA">Link</a></td>
    <td><a href="https://github.com/BlueStamford/MBBLSA">Link</a></td>
    <td><a href="https://github.com/BlueStamford/DDLSA">Link</a></td>
    <td><a href="https://github.com/labxscut/elsa">Link</a></td>
    <td><a href="http://www.gbf.de/SystemsBiology">Link</a></td>
  </tr>
  <tr>
    <td>Language</td>
    <td>R</td>
    <td>Python and C++</td>
    <td>C++</td>
    <td>R</td>
    <td>R</td>
    <td>Python and C++</td>
    <td>-</td>
  </tr>
  <tr>
    <td>Replicated Data</td>
    <td>No</td>
    <td>Yes</td>
    <td>No</td>
    <td>Yes</td>
    <td>Yes</td>
    <td>Yes</td>
    <td>Yes</td>
  </tr>
  <tr>
    <td>Confidence Interval</td>
    <td>No</td>
    <td>Yes</td>
    <td>No</td>
    <td>No</td>
    <td>No</td>
    <td>Yes</td>
    <td>No</td>
  </tr>
  <tr>
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
Identifying local associations in biological time series: algorithms, statistical significance and applications
Dongmei Ai, Lulu Chen, Jiemin Xie, Longwei Cheng, Fang Zhang, Yihui Luan, Yang Li, Shengwei Hou, Fengzhu Sun, Li Charlie Xia*
Briefings in Bioinformatics, 2023 (Accepted)

