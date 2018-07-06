[![Google Group](https://img.shields.io/badge/-Google%20Group-lightgrey.svg)](https://groups.google.com/forum/#!forum/jupyter)
![Read the Docs](https://img.shields.io/readthedocs/jupyter-docker-stacks.svg)
[![](https://images.microbadger.com/badges/version/jupyter/base-notebook.svg)](https://microbadger.com/images/jupyter/base-notebook "Get your own version badge on microbadger.com")



**Example 1:** This command pulls the `jupyter/scipy-notebook` image tagged `2c80cf3537ca` from Docker Hub if it is not already present on the local host. It then starts a container running a Jupyter Notebook server and exposes the server on host port 8888. The server logs appear in the terminal. Visiting `http://<hostname>:8888/?token=<token>` in a browser loads the Jupyter Notebook dashboard page, where `hostname` is the name of the computer running docker and `token` is the secret token printed in the console. The container remains intact for restart after the notebook server exits.

    docker run -p 8888:8888 jupyter/scipy-notebook:2c80cf3537ca

**Example 2:** This command pulls the `jupyter/datascience-notebook` image tagged `e5c5a7d3e52d` from Docker Hub if it is not already present on the local host. It then starts an *ephemeral* container running a Jupyter Notebook server and exposes the server on host port 10000. The command mounts the current working directory on the host as `/home/jovyan/work` in the container. The server logs appear in the terminal. Visiting `http://<hostname>:10000/?token=<token>` in a browser loads JupyterLab, where `hostname` is the name of the computer running docker and `token` is the secret token printed in the console. Docker destroys the container after notebook server exit, but any files written to `~/work` in the container remain intact on the host.

    docker run --rm -p 10000:8888 -e JUPYTER_LAB_ENABLE=yes -v "$PWD":/home/jovyan/work jupyter/datascience-notebook:e5c5a7d3e52d

## Contributing

Please see the [Contributor Guide on ReadTheDocs](http://jupyter-docker-stacks.readthedocs.io/) for information about how to contribute package updates, recipes, features, tests, and community maintained stacks.

## Alternatives

* [jupyter/repo2docker](https://github.com/jupyter/repo2docker) - Turn git repositories into Jupyter-enabled Docker Images
* [openshift/source-to-image](https://github.com/openshift/source-to-image) - A tool for building/building artifacts from source and injecting into docker images
* [jupyter-on-openshift/jupyter-notebooks](https://github.com/jupyter-on-openshift/jupyter-notebooks) - OpenShift compatible S2I builder for basic notebook images

## Resources

* [Documentation on ReadTheDocs](http://jupyter-docker-stacks.readthedocs.io/)
* [Issue Tracker on GitHub](https://github.com/jupyter/docker-stacks)
* [Jupyter Google Group](https://groups.google.com/forum/#!forum/jupyter)
* [Jupyter Website](https://jupyter.org)
