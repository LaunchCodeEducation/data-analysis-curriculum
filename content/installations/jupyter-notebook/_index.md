+++
title = "Installing Jupyter Notebook"
date = 2024-02-12T13:42:28-06:00
draft = false
weight = 5
+++

## Setting up Jupyter Notebook

[Jupyter](https://jupyter.org/) is a non-profit, open-source project that offers various tools and solutions. This course will utilize [Jupyter Notebook](https://jupyter-notebook.readthedocs.io/en/latest/) for documentation and code editing all within your browser.

{{% notice blue Note "rocket" %}}
This course will have you install python packages in your global environment.
{{% /notice %}}

The following commands will install Jupyter Notebook in your global environment:

```console
pip install notebook
```

{{% notice orange Warning "rocket" %}}
If the above command produces an error you may need to specify `pip3` like so:

```console
pip3 install notebook
```
{{% /notice %}}

{{% notice blue Note "rocket" %}}
`pip` is a package manager that is included with any Python installation. You can verify the version and installation of pip by typing in the following command:

**Unix/MacOS**:
```console
python3 -m pip --version
```

**Windows**:
```console
py -m pip --version
```
{{% /notice %}}

### Start the App Server
Open Jupyter Notebook with the following command:

```console
jupyter notebook
```



## Verification

The running application will look similar to the image below:

![Jupyter notebook running on localhost within the browser](pictures/localhost-notebook.png?classes=border)

{{% notice blue Note "rocket" %}}
If a browser window with a running Jupyter notebook application does not happen automatically, you can copy and paste one of the highlighted links into the browser of your choice.
{{% /notice %}}

![Running jupyter notebook in the terminal to open the application](pictures/jupyter-notebook.png?classes=border)

{{% notice orange Warning "rocket" %}}
In order to stop the Jupyter Notebook server from running, open your terminal window where you started the server and press `ctrl + c`. You will be asked to confirm the shutdown process, type in `y` and hit the enter key to confirm.

![Shutting down jupyter notebook server within the command line](pictures/confirm-shutdown.png?classes=border)
{{% /notice %}}