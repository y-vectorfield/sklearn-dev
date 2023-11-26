FROM python:3.8
ARG GROUPNAME=skuser
ARG USERNAME=skuser
ARG UID=1000
ARG GID=1000

RUN apt-get update && apt-get install -y vim
RUN groupadd -g $GID $GROUPNAME && \
    useradd -m -s /bin/bash -u $UID -g $GID $USERNAME
USER $USERNAME
RUN pip install pytest pytest-cov ruff mypy numpydoc black==23.3.0 wheel numpy scipy cython
WORKDIR /home/$USERNAME
