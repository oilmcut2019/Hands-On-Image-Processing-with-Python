FROM ubuntu:14.04
MAINTAINER Haryanto, M07158031@o365.mcut.edu.tw

USER root
WORKDIR /root

RUN apt-get update \
    	&& apt-get upgrade -y \
	&& apt-get install -qqy x11-apps \
    	&& apt-get install -y \
   	build-essential \
	software-properties-common \
    	ca-certificates \
    	dbus-x11 \
	xorg \
	openbox \
    	x11-xserver-utils \
    	gcc \
    	git \
    	libpq-dev \
    	make \
    	mercurial \
    	pkg-config \
    	python3.5 \
    	python3.5-dev \
    	ssh \
	libffi-dev \
	libxml2-dev \
	libxslt1-dev \
        libtiff4-dev \
	libjpeg8-dev \
	zlib1g-dev \
	libfreetype6-dev \
        liblcms2-dev \
	libwebp-dev \
	tcl8.5-dev \
	tk8.5-dev \
	python3-pyqt4 \
	imagemagick \
	libfontconfig-dev \
	fonts-noto-cjk \
	python3-tk \
	ttf-mscorefonts-installer \
	&& fc-cache \
    	&& apt-get autoremove \
    	&& apt-get clean

ADD https://raw.githubusercontent.com/pypa/pip/5d927de5cdc7c05b1afbdd78ae0d1b127c04d9d0/contrib/get-pip.py /root/get-pip.py
RUN python3.5 /root/get-pip.py
RUN pip3.5 install -U "setuptools" \
	"scikit-learn" \
	"matplotlib==2.0" \
	"numpy==1.14.5" \
	"scipy==0.19" \
	"pillow==5.1.0" \
	"numpydoc==0.6" \
	"scikit-image==0.14.0" \
	"jupyter" \
	"notebook" \
	"QtPy==1.2" \
	"decorator==4.4.0" \
	"qtconsole==4.3" \
	"QtAwesome==0.4" \
	"imageio==2.5" \
	"imagesize==1.1.0" \
	"image" \
	"h5py==2.9.0" \
	"ipywidgets==7.4.2" \
	"opencv-python==3.4.2.16" \
	"Python-fontconfig" \
	"wordcloud" \
	"tornado" \
	"opencv-contrib-python==3.4.2.16" \
	"networkx==1.11" \
	"SimpleITK" \
	"Keras==2.2.4" \
	"tensorflow==1.14" \
	"tensorboard==1.14" \
	"pandas" \
	"dask" \
	"imutils"
	
RUN pip3.5 install -U "jupyter_contrib_nbextensions" \
	&& jupyter contrib nbextension install \
	&& jupyter nbextension enable codefolding/main \
	&& jupyter nbextension enable toc2/main \
	&& jupyter nbextension enable snippets_menu/main \
	&& jupyter nbextension enable nbTranslate/main \
	&& jupyter nbextension enable varInspector/main


RUN jupyter nbextension install https://rawgit.com/jfbercher/small_nbextensions/master/highlighter.zip  --user \
	&& jupyter nbextension enable highlighter/highlighter
 
WORKDIR /home

RUN git clone https://github.com/oilmcut2019/Hands-On-Image-Processing-with-Python.git --branch=student

RUN pip3.5 install ipython

EXPOSE 7745

ADD run_jupyter.sh /root
RUN chmod +x /root/run_jupyter.sh

ENV LC_ALL=C.UTF-8
ENV LANG=C.UTF-8

CMD ["/root/run_jupyter.sh"]
