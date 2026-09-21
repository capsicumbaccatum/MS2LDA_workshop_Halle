# MS2LDA_workshop_Halle
Workshop material for the MS2LDA workshop on September 29, 2026 at the IPB in Halle (Germany)

# Get started

## Install MS2LDA
Follow this guide on GitHub to install MS2LDA on your computer: https://github.com/vdhooftcompmet/MS2LDA/blob/main/README_CONDA.md
This requires the installation of Anaconda or Miniconda prior to cloning the MS2LDA GiHub repository via "git clone".

## Download the model
You need to download the model prior to any analysis (see guide linked above, step 4).
```
./run_analysis.sh --only-download
```

## Download the demo dataset (from here)
You can download the demo dataset from this repository. Please find it in the folder: Original_feature_Table.
This is a demo dataset for this workshop in MGF format. 
If you do *not* want to map the resulting Mass2motifs on a molecular network, you can proceed with running MS2LDA directly on this file.
For Feature-Based Molecular Networking (FBMN), the MGF file can also be taken directly as input for MS2LDA.

For Classical Molecular Networking (CMN), we need to use the consensus MGF file provided by GNPS2.
You can find this consensus MGF file in this folder: GNPS2_files.


# Optional: Run GNPS2 Classical Molecular Networking on the demo dataset
- Optional Run GNPS2 yourself and Download the consensus MGF file yourself. 
Of course, please feel free to run the Classical molecular Networking workflow on GNPS2 yourself. You can find GNPS2 here: https://gnps2.org/homepage 
Please be aware that you need an account. 
You can then download the consensus spectra MGF file from the task website. 

You can find the CMN graphml file also in this folder: GNPS2_files.
Please load this file into Cytoscape using: File -> Import -> Network from File 
You can then adapt the layout and style to your convenience.

# Run MS2LDA on the demo dataset 
If you want to map the motifs on the GNPS2 network, you'll need to run MS2LDA on the consensus MGF file. 
Follow the guide here: https://github.com/vdhooftcompmet/MS2LDA/blob/main/QUICK_START.md

# Run MS2LDA network mappings on the GNPS2 molecular network consensus MGF

You can find and download the CLI script here: https://github.com/capsicumbaccatum/MS2LDA_Molecular_network_mapping
Follow the guide and run the script, using the consensus MGF file, and the MS2LDA output.
If you could not run MS2LDA successfully, but still want to try out the molecular network mapping, you can find the MS2LDA demo output files in this folder: MS2LDA_output.

If the network mapping script does not work for you, you can also download the resulting files from this folder: motif_mapping_output
For mapping the Mass2Motifs on your network, please use the wise format data table.
The long format data table may be used for mapping on phylogenetic trees, or for other statistical analysis.

# Map the long format CSV table on the network in Cytoscape

In Cytoscape import the table using File -> Import -> Table from file.
Please make sure to use "shared.name" as the mapping key for your network, and "feature_id" as the mapping key for the table.

# Helpful links and references:

Original GitHub repository: https://github.com/vdhooftcompmet/MS2LDA/tree/main
MS2LDA network mapping GitHub repository: https://github.com/capsicumbaccatum/MS2LDA_Molecular_network_mapping

MS2LDA tutorials on YouTube: https://www.youtube.com/playlist?list=PLCFXpjU30dmHm1ypoEnWnZ1vcJhR4awPo
