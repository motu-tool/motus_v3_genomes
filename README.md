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



The script automatically checks that the downloaded file md5 is correct.

The data will be downloaded in the same repository where the script is located, under a repository with the name `motus_v3_genomes`.
The structure is as follow:
- Within `motus_v3_genomes` there is a repository per mOTU
- Within each mOTU repository there is a file `1.list_files.txt` with the path to the files, and the files of the genomes are within the mOTU directory
- If you do `motus_genomes_download -m all` an additional file `1.list_all_files.txt` will be created within `motus_v3_genomes`.

Note that all files are first downloaded to `motus_v3_genomes/temp_dir` and moved to the final destination once the download and unzip is complete.


Finally, you can list all motus and the number of associated genomes with:
```
python motus_genomes_download -l
```

And you can list all genomes with:
```
python motus_genomes_download -g
```
