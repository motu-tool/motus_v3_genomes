Download  mOTUs 3 genomes
========

This tool allows to download all or any of the 700,000 genomes used for the mOTUs 3 database. The user can download a specific genome (type), all genomes associated with a specific mOTU, or the complete database.

## Installation 
To run the script, clone this repository

```
git clone https://github.com/motu-tool/motus_v3_genomes
cd motus_v3_genomes
```

## Downloading genomes

The data will be downloaded into the same folder where the script is located, under a folder with the name `motus_v3_genomes`.

The structure is as follows:
- Within `motus_v3_genomes` there is a folder for each mOTU
- Within each mOTU folder are the genomes associated with this mOTU. In addition,  there is a file `1.list_files.txt`. This file lists the paths to each of the downloaded genome files.
- If you run `motus_genomes_download -m all`, an additional file `1.list_all_files.txt` will be created within `motus_v3_genomes`.

Note that all files are first downloaded to `motus_v3_genomes/temp_dir` and moved to the final destination once the download and unzip are complete.

The script automatically checks the md5 sum of each of the downloaded files.


To download one genome type (for example the MAG `LIAN20-1_SAMN11649416_METAG_000035`):

```
python motus_genomes_download -m LIAN20-1_SAMN11649416_METAG_000035
```

To download all genomes from one mOTU (for example the ref mOTU `ref_mOTU_v3_00006`):
```
python motus_genomes_download -m ref_mOTU_v3_00006
```

If you run the two commands above to download a genome and mOTU, you will end up with the following structure:
```
.
|-- README.md
|-- motus_genomes_download
`-- motus_v3_genomes
    |-- ext_mOTU_v3_19213
    |   |-- 1.list_files.txt
    |   |-- LIAN20-1_SAMN11649406_METAG_001584.fa
    |   `-- LIAN20-1_SAMN11649416_METAG_000035.fa
    |-- ref_mOTU_v3_00006
    |   |-- 1.list_files.txt
    |   |-- 1218103.SAMD00041821.fa
    |   |-- 1340435.SAMN02440767.fa
    |   `-- 253.SAMN05421692.fa
    `-- temp_dir
```

To download all genomes:
```
python motus_genomes_download -m all
```

Finally, you can list all mOTUs and the number of associated genomes (available for download) with:
```
python motus_genomes_download -l
```

And you can list all genomes with:
```
python motus_genomes_download -g
```
