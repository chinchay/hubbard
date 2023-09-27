
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

