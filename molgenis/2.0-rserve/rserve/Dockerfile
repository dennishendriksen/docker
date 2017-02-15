FROM r-base:3.3.2

RUN apt-get update \ 
	&& apt-get install -y --no-install-recommends \
		libcurl4-openssl-dev \
		libssl-dev \
		openssl \
	&& rm -rf /var/lib/apt/lists/*
	
ADD install-packages.R /
RUN Rscript install-packages.R

EXPOSE 6311

RUN useradd -ms /bin/bash r
ADD start.R start.R
RUN chown r start.R
ADD Rserv.conf /Rserv.conf
RUN chown r /Rserv.conf

#USER r
CMD Rscript start.R