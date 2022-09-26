Download genomes used for mOTUs 3
========

This tool downloads the 700,000 genomes used for the mOTUs 3 database.

First, clone this repository
```
git clone https://github.com/motu-tool/motus_v3_genomes
cd motus_v3_genomes
```

To download one genome type (for example the MAG `LIAN20-1_SAMN11649416_METAG_000035`):
```
python motus_genomes_download -m LIAN20-1_SAMN11649416_METAG_000035
```

To download all genomes from one motu (for example the ref mOTU `ref_mOTU_v3_00006`):
```
python motus_genomes_download -m ref_mOTU_v3_00006
```

To download all genomes:
```
python motus_genomes_download -m all
```



The script automatically checks the md5 sum of the downloaded file.

The data will be downloaded in the same folder where the script is located, under a folder with the name `motus_v3_genomes`.
The structure is as follows:
- Within `motus_v3_genomes` there is a folder per mOTU
- Within each mOTU folder there is a file `1.list_files.txt` with the path to the files, and the files of the genomes are within the mOTU directory
- If you run `motus_genomes_download -m all` an additional file `1.list_all_files.txt` will be created within `motus_v3_genomes`.

Note that all files are first downloaded to `motus_v3_genomes/temp_dir` and moved to the final destination once the download and unzip is complete.

If you run the two commands listed above to download a genome and mOTU, you will end up with the following structure:
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

Finally, you can list all motus and the number of associated genomes (available for download) with:
```
python motus_genomes_download -l
```

And you can list all genomes with:
```
python motus_genomes_download -g
```
