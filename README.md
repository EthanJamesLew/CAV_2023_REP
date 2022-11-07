# Repeatability Evaluation Package.

NOTE: for local runs, you will need to have CUDA >=11.7 (for docker) installed!

This is the repeatability evaluation package for the tool paper "AutoKoopman: A Toolbox for Automated System Identification via Koopman Operator Linearization", submitted to HSCC 2023.

The link to the package Code Ocean capsule is: https://codeocean.com/capsule/8837388/tree/v1 . We expect the run to take about 3.5 hours to complete.

This REP repeats the results

- the performance and time metrics for the symbolic, black box, and real data seen in Table 1 separately
- Figures 2, 3, and 4

## Instructions

### Run on CodeOcean

In this package, we provide a Code Ocean capsule to allow reproducible runs, available here: https://codeocean.com/capsule/8837388/tree/v1 . If viewed and evaluated from a web browser, we require no additional tools or libraries before usage. The main README.md in the code subdirectory contains an overview of the package. The run script in the code subdirectory repeats all of the experiments. Hitting the "Reproducible Run" button will initiate a repeat of the artifacts mentioned.

### Run Locally

To run the package locally, you can download the capsule from Code Ocean as a docker image. You will need to have docker installed. Visit the capsule webpage at https://codeocean.com/capsule/8837388/tree/v1 and go the main menu Capsule->Export. In the Export compute capsule menu, select "Include data 79.73 MB". Unzip the dowloaded file, and navigate to the directory. The run instructions are available in REPRODUCING.md, with the main command being

```shell
docker run --rm --gpus all \
  --workdir /code \
  --volume "$PWD/data":/data \
  --volume "$PWD/code":/code \
  --volume "$PWD/results":/results \
  registry.codeocean.com/published/897bcbe3-1d73-4305-b3b9-870663cd6cab:v1 bash run
```

NOTE: if you want to follow REPRODUCING.md, you will need to set run to an executable via `chmod +x run`.

If you want to modify some files and re-run some of the experiment, you can open an interactive shell via

```shell
docker run --rm --gpus all \
  --workdir /code \
  --volume "$PWD/data":/data \
  --volume "$PWD/code":/code \
  --volume "$PWD/results":/results \
  registry.codeocean.com/published/897bcbe3-1d73-4305-b3b9-870663cd6cab:v1 -it /bin/bash
```

## Additional Information

(not required for REP) The Autokoopman tool source code is available at https://github.com/EthanJamesLew/AutoKoopman.git . With a python 3.8+ environment, the library can be installed via pip

```shell
cd <AutoKoopman repo root>
pip install .
```

This package will be published on PyPI after review.
