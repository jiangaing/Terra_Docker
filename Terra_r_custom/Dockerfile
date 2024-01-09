FROM us.gcr.io/broad-dsp-gcr-public/terra-jupyter-r:2.2.1

USER root

################# custom tools #################
COPY mamba-requirements.yaml /etc/terra-docker/
RUN conda install -c conda-forge mamba
RUN mamba env update -f /etc/terra-docker/mamba-requirements.yaml
################# end custom tools section ######

RUN R -e 'BiocManager::install(c( \
    "AnVIL", \
    "SingleCellExperiment", \ 
    "GenomicFeatures", \
    "GenomicAlignments", \ 
    "ShortRead", \
    "DESeq2", \
    "AnnotationHub", \
    "ExperimentHub", \
    "ensembldb", \
    "scRNAseq", \
    "scran", \
    "Rtsne"))'

USER jupyter