# CasaOs JupyterLab Docker Stacks Oficial image Compose

[![GitHub actions badge](https://github.com/jupyter/docker-stacks/actions/workflows/docker.yml/badge.svg)
](https://github.com/jupyter/docker-stacks/actions/workflows/docker.yml?query=branch%3Amain "Docker images build status")
[![Read the Docs badge](https://img.shields.io/readthedocs/jupyter-docker-stacks.svg)](https://jupyter-docker-stacks.readthedocs.io/en/latest/ "Documentation build status")
[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/jupyter/docker-stacks/main.svg)](https://results.pre-commit.ci/latest/github/jupyter/docker-stacks/main "pre-commit.ci build status")
[![Discourse badge](https://img.shields.io/discourse/users.svg?color=%23f37626&server=https%3A%2F%2Fdiscourse.jupyter.org)](https://discourse.jupyter.org/ "Jupyter Discourse Forum")
[![Binder badge](https://static.mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/jupyter/docker-stacks/main?urlpath=lab/tree/README.ipynb "Launch a quay.io/jupyter/base-notebook container on mybinder.org")

Runing JupyterLab Notebook on CasaOS Server with aarch64
Based on [jupyterLab Base Notebook](https://quay.io/repository/jupyter/base-notebook)
Based on [Docker-Stacks](https://github.com/jupyter/docker-stacks)
- How to use:
1. On Casaos Home.
2. click on "+".
3. Click on add custom image.
4. Click on import icon.
5. select the JupyterLab.yaml
- to change your docker external port, edit the [JupyterLab.yaml](https://github.com/hqnicolas/CasaOsJupyterLabStacks/blob/main/jupyterlab.yaml)
```
published: "3000"
```
- Now you can aceess: http://casaos.yourserver:3000
- How to access the login token:
1. On Casaos Home
2. Click on JupyterLab Config
3. Click on Terminal and Logs
4. on Logs, Find this line:
```
[I 2023-11-12 19:08:57.681 ServerApp] Jupyter Server 2.10.0 is running at:
[I 2023-11-12 19:08:57.682 ServerApp] http://7371962312567:8888/lab?token=10bba6428018b6d3f913231231
```
5. Take the token from Link above.
6. Drop the token on your JupyterLab Login Screen.
- [This file](https://github.com/hqnicolas/CasaOsJupyterLabStacks/blob/main/jupyterlab.yaml) is Based on Comand:
```
podman pull quay.io/jupyter/base-notebook
docker run -it --rm -p 3000:8888 -v "${PWD}":/home/jovyan/work quay.io/jupyter/base-notebook
``` 
- Your Jupiter will access your USER folder From CasaOS Linux server.

## Choosing Jupyter frontend

JupyterLab is the default for all the Jupyter Docker Stacks images.
It is still possible to switch back to Jupyter Notebook (or to launch a different startup command).
You can achieve this by passing the environment variable `DOCKER_STACKS_JUPYTER_CMD=notebook` (or any other valid `jupyter` subcommand) at container startup;
more information is available in the [documentation](https://jupyter-docker-stacks.readthedocs.io/en/latest/using/common.html#alternative-commands).

## Resources

- [Documentation on ReadTheDocs](https://jupyter-docker-stacks.readthedocs.io/en/latest/)
- [Issue Tracker on GitHub](https://github.com/jupyter/docker-stacks/issues)
- [Jupyter Discourse Forum](https://discourse.jupyter.org/)
- [Jupyter Website](https://jupyter.org)
- [Images on Quay.io](https://quay.io/organization/jupyter)

## Using old images

This project only builds one set of images at a time.
If you want to use older `Ubuntu` and/or `python` version, you can use following images:

| Build Date   | Ubuntu | Python | Registry  | Tag            |
| ------------ | ------ | ------ | --------- | -------------- |
| 2022-10-09   | 20.04  | 3.7    | docker.io | `1aac87eb7fa5` |
| 2022-10-09   | 20.04  | 3.8    | docker.io | `a374cab4fcb6` |
| 2022-10-09   | 20.04  | 3.9    | docker.io | `5ae537728c69` |
| 2022-10-09   | 20.04  | 3.10   | docker.io | `f3079808ca8c` |
| 2022-10-09   | 22.04  | 3.7    | docker.io | `b86753318aa1` |
| 2022-10-09   | 22.04  | 3.8    | docker.io | `7285848c0a11` |
| 2022-10-09   | 22.04  | 3.9    | docker.io | `ed2908bbb62e` |
| 2023-05-30   | 22.04  | 3.10   | docker.io | `4d70cf8da953` |
| weekly build | 22.04  | 3.11   | quay.io   | `latest`       |

## Contributing

Please see the [Contributor Guide on ReadTheDocs](https://jupyter-docker-stacks.readthedocs.io/en/latest/)
for information about how to contribute recipes, features, tests, and community maintained stacks.

## Alternatives

- [jupyter/repo2docker](https://github.com/jupyterhub/repo2docker) -
  Turn git repositories into Jupyter-enabled Docker Images
- [openshift/source-to-image](https://github.com/openshift/source-to-image) -
  A tool for building artifacts from source and injecting them into docker images
- [jupyter-on-openshift/jupyter-notebooks](https://github.com/jupyter-on-openshift/jupyter-notebooks) -
  OpenShift compatible S2I builder for basic notebook images
