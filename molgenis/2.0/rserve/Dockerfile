FROM r-base:3.3.2

ADD install-packages.R /
RUN Rscript install-packages.R

EXPOSE 6311

ADD start.R start.R
ADD Rserv.conf /Rserv.conf
CMD Rscript start.R