+++
title = "Installing Jupyter Notebook"
date = 2024-02-12T13:42:28-06:00
draft = false
weight = 18
+++

## Setting up Jupyter Notebook

[Jupyter](https://jupyter.org/) is a non-profit, open-source project that offers various tools and solutions. This course will utilize [Jupyter Notebook](https://jupyter-notebook.readthedocs.io/en/latest/) for documentation and code editing all within your browser.

The following command will install Jupyter Notebook onto your machine:

```console
pip install notebook
```

### Start the App Server
Open Jupyter Notebook with the following command:

```console
jupyter notebook
```

## Verification

The running application will look similar to the image below:

![Jupyter notebook running on localhost within the browser](pictures/localhost-notebook.png?classes=border)

{{% notice blue Note "rocket" %}}
If a browser window with a running jupyter notebook application does not happen automatically, you can copy and paste one of the highlighted links into the browser of your choice.
{{% /notice %}}

![Running jupyter notebook in the terminal to open the application](pictures/jupyter-notebook.png?classes=border)

{{% notice orange Warning "rocket" %}}
In order to stop the Jupyter Notebook server from running, open your terminal window where you started the server and press `ctrl + c`. You will be asked to confirm the shutdown process, type in `y` and hit the enter key to confirm.

![Shutting down jupyter notebook server within the command line](pictures/confirm-shutdown.png?classes=border)
{{% /notice %}}