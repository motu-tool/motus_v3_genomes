Download genomes used for mOTUs 3
========

This tool downloads the 700,000 genomes used for the mOTUs 3 database.

First, clone this repository
```
git clone https://github.com/motu-tool/motus_v3_genomes
```

To download one genome type (for example the reference genome `100053.SAMN02947772`):
```
motus_genomes_download -m 100053.SAMN02947772
```

To download all genomes from one motu (for example the ref mOTU `ref_mOTU_v3_00001`):
```
motus_genomes_download -m ref_mOTU_v3_00001
```

To download all genomes:
```
motus_genomes_download -m all
```

You can specify the path where to save the files as
```
motus_genomes_download -m ref_mOTU_v3_00001 -p /path/to/dir/
```

Which will create a repository and save the result within.


Finally, you can list all motus and the number of associated genomes with:
```
motus_genomes_download -l
```
