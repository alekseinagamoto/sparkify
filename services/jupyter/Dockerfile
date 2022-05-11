FROM jupyter/minimal-notebook

WORKDIR /home/$NB_USER/work

# change active user to root
USER root 

# RUN mkdir /src /data

# # set jovyan as owner of directories
# RUN chown $NB_UID /src /data

COPY ./data ./data
COPY ./src ./src
COPY poetry.lock pyproject.toml ./

RUN pip3 install poetry
RUN poetry config virtualenvs.create false
RUN poetry install --no-dev

# # change back to user jovyan
# USER $NB_UID