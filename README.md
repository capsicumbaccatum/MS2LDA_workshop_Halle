# MS2LDA_workshop_Halle
Workshop material for the MS2LDA workshop on September 29, 2026 at the IPB in Halle (Germany)

# Get started

## Install MS2LDA
Follow this guide on GitHub to install MS2LDA on your computer: https://github.com/vdhooftcompmet/MS2LDA/blob/main/README_CONDA.md
This requires the installation of Anaconda (https://www.anaconda.com/download) or Miniconda prior to cloning the MS2LDA GitHub repository via "git clone".

## Download the model
You need to download the model prior to any analysis (see guide linked above, step 4).
```
./run_analysis.sh --only-download
```

## Download the demo dataset (attached to the course invitation email, or available in this repository)
File name: FeatureTable_Test_Course.mgf

The file has been attached to the invitation email for this workshop.
You can also download the demo dataset from this repository. Please find it in the folder: Original_feature_Table.
This is a demo dataset for this workshop in MGF format. 

**Now you have two options:**

1. Skip Mass2Motif mapping on a molecular network: Run MS2LDA directly on the demo dataset (FeatureTable_Test_Course.mgf)
If you do *not* want to map the resulting Mass2motifs on a molecular network, you can proceed with running MS2LDA directly on this file.

You can use this command (please adapt paths to input and output files accordingly):
On Windows cmd
```
./run_analysis.sh --dataset "path\to\FeatureTable_Test_Course.mgf" --n-motifs 200 --n-iterations 1000 --output-folder "path\to\output_folder_demo"
```

2. Include Mass2Motif mapping on a molecular network: Run MS2LDA on the consensus spectra MGF of the demo dataset (FeatureTable_Test_Course_consensus.mgf)
For Classical Molecular Networking (CMN), we need to use the consensus MGF file provided by GNPS2.
You can find this consensus MGF file in this folder: GNPS2_files.

If you want to map the motifs on the GNPS2 network, you'll need to run MS2LDA (again) on the consensus MGF file. 
It is not necessary to run MS2LDA on both files (FeatureTable_Test_Course.mgf **and** FeatureTable_Test_Course_consensus.mgf), but just on the latter consensus MGF file to proceed with the mapping on the molecular network. Please note that the results and especially the feature IDs will not be exactly the same.

To run MS2LDA on the consensus MGF, you can use this command (please adapt paths to input and output files accordingly):
(Windows cmd)

```
./run_analysis.sh --dataset "path\to\FeatureTable_Test_Course.mgf" --n-motifs 200 --n-iterations 1000 --output-folder "path\to\output_folder_demo"
```

Note: For Feature-Based Molecular Networking (FBMN), the MGF file can also be taken directly as input for MS2LDA.
Please be aware that for running the FBMN workflow on GNPS, you need to provide a quantification table in addition to the aligned spectra MGF file.
For this workshop, we only have an aligned spectra MGF file. Therefore, we use CMN to showcase the Mass2Motif mapping (option 2). This results in different feature IDs for the molecular network, and hence we need to run MS2LDA on the consensus MGF file.




##  Optional: Run GNPS Classical Molecular Networking on the demo dataset yourself
Of course, please feel free to run the Classical molecular Networking workflow on GNPS(2) yourself. You can find GNPS2 here: https://gnps2.org/homepage 
Please be aware that you need an account to run the workflow, and that you will need to upload the MGF file first. 
You can then download the consensus spectra MGF file from the task website once the workflow has completed. Important: It is necessary to change the field "SCANS" to "FEATURE_ID" in the consensus spectra MGF file you download from GNPS. 

You can find the CMN graphml file also in this folder: GNPS2_files.
Please load this file into Cytoscape using: File -> Import -> Network from File 
You can then adapt the layout and style to your convenience.




# Run MS2LDA network mappings on the GNPS2 molecular network consensus MGF

If you could not run MS2LDA successfully, but still want to try out the molecular network mapping, you can find the MS2LDA demo output files in this folder: MS2LDA_output.

You can find and download the CLI script here: https://github.com/capsicumbaccatum/MS2LDA_Molecular_network_mapping
You need to download/clone the repository to your computer.

Follow the guide and run the script "MS2LDA_network_mappings_v1.0.py", using the consensus MGF file, and the MS2LDA output.

To run MS2LDA_network_mappings.py on the consensus MGF, you can use this command (please adapt paths to input and output files accordingly):
(Windows cmd)
```
python "path\to\MS2LDA_network_mappings_v1.0.py" --mgf "path\to\FeatureTable_Test_Course_consensus.mgf" --model "path\to\ms2lda.bin" --viz "path\to\ms2lda_viz.json.gz" --outdir "demo_results"
```


If the network mapping script does not work for you (or if the allocated time is not sufficient), you can also download the resulting files from this folder: motif_mapping_output. 
For mapping the Mass2Motifs on your network, please use the wide format data table.

Note: The long format data table may be used for mapping on phylogenetic trees, or for other statistical analysis.

# Map the wide format CSV table on the network in Cytoscape

In Cytoscape import the table using File -> Import -> Table from file.
Please make sure to use "shared.name" as the mapping key for your network, and "feature_id" as the mapping key for the table.

# Helpful links and references:

Original GitHub repository: https://github.com/vdhooftcompmet/MS2LDA/tree/main
MS2LDA network mapping GitHub repository: https://github.com/capsicumbaccatum/MS2LDA_Molecular_network_mapping

MS2LDA tutorials on YouTube: https://www.youtube.com/playlist?list=PLCFXpjU30dmHm1ypoEnWnZ1vcJhR4awPo
