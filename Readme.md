# Lattice dataset for the paper "Simulating rare kaon decays $K^{+}\to\pi^{+}\ell^{+}\ell^{-}$ using domain wall lattice QCD with physical light quark masses"

This repository contains the tool and access credentials to download the correlation functions produced and analysed in [arXiv:2202.08795](https://arxiv.org/abs/2202.08795). This dataset was produced by the measurement program posted [here]() based on the [Grid](https://github.com/paboyle/Grid) and [Hadrons](https://github.com/aportelli/Hadrons) libraries.

The dataset is hosted on the [Storj](https://www.storj.io/) decentralised cloud storage. This repository contains a set of automatised scripts to download and unpack the dataset on a UNIX OS and does not require any non-standard dependency to be installed.

## Quick start
```bash
./bootstrap.sh             # sets up an embedded rclone
./download.sh              # warning: downloads 260 GB of data
less data/README.txt       # read data description
./expand.sh k000_p100/2pt  # example: expand 2-point functions
                           # cf. possible paths in README.txt
```

## Detailed instructions
### Using embedded Rclone (self-contained, the simplest)
To download the dataset, start by bootstrapping a local, dedicated [Rclone](https://rclone.org/) installation by executing `./bootstrap.sh` without arguments. This step is necessary even if you have Rclone installed, this script sets up an Rclone installation with credential to Storj DCS confined within the script directory, to avoid interfering with a system-wide Rclone installation.

Once Rclone is setup, execute `./download.sh` without arguments to download the dataset. *If downloading the dataset on a personal computer, please note that the total dataset has a size of 260 GB, and as much space is required to unarchive it.*

Once the dataset is downloaded, it can be unarchived using the command `./expand.sh` without argument. Once expanded, all the files of the form `*.tar.*` can be savely removed.

### Using S3