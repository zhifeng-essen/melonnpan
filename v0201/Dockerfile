# Use the biobakery base image
FROM biobakery/base:1.1

RUN /opt/conda/bin/conda install -c hcc melonnpan && \
    ln -s /opt/conda/lib/libgfortran.so.4 /opt/conda/lib/libgfortran.so.3 && \
    /opt/conda/bin/conda install r-optparse r-genabel -c bioconda && \
    /opt/conda/bin/conda install r-ggplot2 r-tibble r-dplyr -c r && \
    R -e "install.packages('AssocTests')" && \
    cd opt/ && \
    git clone https://github.com/biobakery/melonnpan.git && \
    R CMD INSTALL melonnpan && \
    /opt/conda/bin/conda clean --all --yes
    
