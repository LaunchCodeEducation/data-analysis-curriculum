+++
title = "Installing Python"
date = 2024-02-12T13:42:28-06:00
draft = false
weight = 17
+++

## Setting up Python

Installing Python on your computer also includes the [pip](https://pip.pypa.io/en/stable/index.html) package installer by default. `pip` is a tool that is used to install project dependencies like [pandas](https://pandas.pydata.org/), [Jupyer Notebook](https://jupyter.org/install), [NumPy](https://numpy.org/),[FastAPI](https://fastapi.tiangolo.com/), and many others. `pip` will be used in future installation sections to install tools onto your machine.

To begin the installation process click on the link below:

{{% notice blue "Installation Link" "rocket" %}}
[Install Python](https://www.python.org/downloads/)
{{% /notice %}}

The image below depicts the downloads page for Python. Within the highlighted area select your operating system.

![Python downloads page](pictures/download-python.png?classes=border)

## Windows Users

Download the most recent stable release for the `Windows` operating system. At the time of writing this the most recent stable version is `3.11.8`.

![Windows stable release for python3 highlighted on the windows operating system download page for python](pictures/stable-release-windows.png?classes=border)

## MacOS Users

Download the most recent stable release for the `MacOS` operating system. At the time of writing this the most recent stable version is `3.11.8`.

![MacOS stable release for python3 highlighted on the MacOS operating system download page for python](pictures/stable-release-mac.png?classes=border)

### Verification

Once you have downloaded python open up your terminal and type in the following command:

```console
python3 --version
```

The following should be returned as output:

```console
Python 3.x.x
```