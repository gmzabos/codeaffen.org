---
layout: page
title: p3exporter
subtitle: Python programable Prometheus exporter
tags: [project, prometheus, exporter, python]
gh-repo: codeaffen/p3exporter
gh-badge: [star, watch, fork, follow]
---

## Python programmable Prometheus exporter

This repo should help any DevOps to quickstart its Prometheus exporter development base on Python. It is a POC which shows how different packages and libraries can be put together to create your own exporter for Prometheus.

The project is based on Flask as web framework and Prometheus [python-client](python-client). We also provide a simple Dockerfile to enable you to build a Docker container image for your exporter as well as let it run as a simple program.

### install and run locally

To install the `p3exporter` package you simply run the following command inside the project directory:

```text
$ pip install -e .
Obtaining file:///home/nero/Development/p3exporter
...
Installing collected packages: p3exporter
  Running setup.py develop for p3exporter
Successfully installed p3exporter
```

From now you can run it with:

```text
$ p3exporter
INFO:root:Start exporter, listen on 5876
```

#### available command line options

Do determine the available command line options you can call the online help:

```text
$ p3exporter --help
usage: p3exporter [-h] [-c CONFIG_FILE] [-p PORT]

Python programmable Prometheus exporter.

optional arguments:
  -h, --help            show this help message and exit
  -c CONFIG_FILE, --config-file CONFIG_FILE
                        path to configuration file.
  -p PORT, --port PORT  exporter exposed port
```

### build image and run in docker

To let the exporter run in docker you have to do the following:

```text
$ docker build -t codeaffen/p3exporter .
Sending build context to Docker daemon  181.8kB
...
Successfully built a6bdf60489f5
Successfully tagged codeaffen/p3exporter:latest
```

Now you can start the container. Don't forget to expose the port to your network.

```text
$ docker run -d -p 5876:5876 --name p3e codeaffen/p3exporter
03e287d50cce595cec6ee66d75a663a094ba7688c761303e7e1e9ad39bde695c
```

### access exporter

If your exporter run either as local program or as docker container you can access it with your webbrowser.

![metrics in browser](../../assets/img/p3e_metrics.png){: .mx-auto.d-block :}

## further resources

To get more information you can use the following sources:

* [documentation](https://p3exporter.readthedocs.io/en/develop){:target="_blank"}
* [github repository](https://github.com/codeaffen/p3exporter){:target="_blank"}
* [pypi repository](https://pypi.org/project/p3exporter/){:target="_blank"}
* [dockerhub repository](https://hub.docker.com/r/codeaffen/p3exporter){:target="_blank"}
