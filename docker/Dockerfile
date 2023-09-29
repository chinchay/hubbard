
# example taken from https://github.com/cmplopes/alpine-gfortran/blob/master/latest/Dockerfile
FROM alpine:3.15

RUN apk add --no-cache bash bash-doc bash-completion
RUN apk add --no-cache musl-dev 
RUN apk add --no-cache gfortran gdb make
RUN apk add --no-cache vim

# from https://stackoverflow.com/questions/62554991/how-do-i-install-python-on-alpine-linux
# Install python/pip
ENV PYTHONUNBUFFERED=1
RUN apk add --update --no-cache python3 && ln -sf python3 /usr/bin/python
RUN python3 -m ensurepip
RUN pip3 install --no-cache --upgrade pip setuptools
RUN apk add --update --no-cache python3-dev  ## https://stackoverflow.com/questions/21530577/fatal-error-python-h-no-such-file-or-directory

RUN pip3 install numpy

# how to run https://www.numfys.net/howto/F2PY/
# https://www.matecdev.com/posts/fortran-in-python.html
# https://www.matecdev.com/posts/fortran-in-python.html#:~:text=There%20are%20basically%20two%20basic,Cython%20on%20the%20Python%20side.
# python3 -m numpy.f2py -c -m myflib my_fortran_lib.f90


# to install Jupyter
RUN apk add linux-headers # https://github.com/giampaolo/psutil/issues/872
RUN pip install jupyter

CMD ["jupyter", "notebook", "--ip", "0.0.0.0", "--port", "8888", "--no-browser", "--allow-root"] 

# docker build -t alpine .
# docker run -it --rm -p 8888:8888 alpine
# rodar Jupyter:
# jupyter notebook --ip 0.0.0.0 --port 8888 --no-browser --allow-root
# https://stackoverflow.com/questions/38830610/access-jupyter-notebook-running-on-docker-container
# access on browser http://localhost:8888
# although it will ask your password, better copy paste from the terminal the address of the following shape:
# http://127.0.0.1:8888/tree?token=0842b81834718380af7e2a6ff37b7aa61ffb9fe2864dc871

