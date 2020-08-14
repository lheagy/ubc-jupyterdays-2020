**[notebooks](#Notebooks) | [motivating example](#Motivating-Example-Atmospheric-Carbon-Dioxide) | [installing](#Installing) | [widgets](#Jupyter-widgets) | [voila](#Voila-Dashboards)**

# ubc-jupyterdays-2020-widgets
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/lheagy/ubc-jupyterdays-2020-widgets/master?urlpath=lab)
[![Syzygy](https://img.shields.io/badge/launch-syzygy-important)](https://ubc.syzygy.ca/jupyter/hub/user-redirect/git-pull?repo=https%3A%2F%2Fgithub.com%2Flheagy%2Fubc-jupyterdays-2020-widgets&urlpath=tree%2Fubc-jupyterdays-2020-widgets%2F&branch=master)
[![Build Status](https://travis-ci.org/lheagy/ubc-jupyterdays-2020-widgets.svg?branch=master)](https://travis-ci.org/lheagy/ubc-jupyterdays-2020-widgets)

Here, we will use a motivating example that looks at CO2 data to demonstrate interactive computing with:
- [Jupyter Widgets](https://ipywidgets.readthedocs.io/en/latest/index.html) and 
- [Voilà dashboards](https://voila.readthedocs.io/en/latest/?badge=latest)

The example we follow is adapted from the [Intro-Jupyter tutorial from ICESat-2Hackweek](https://github.com/ICESAT-2HackWeek/intro-jupyter), which has contributions from: [Shane Grigsby (@espg)](https://github.com/espg), [Lindsey Heagy (@lheagy)](https://github.com/lheagy), [Yara Mohajerani (@yaramohajerani)](https://github.com/yaramohajerani), and [Fernando Pérez (@fperez)](https://github.com/fperez). 

## Notebooks
- UBC Students & Faculty can run on Syzygy: [![Syzygy](https://img.shields.io/badge/launch-syzygy-important)](https://ubc.syzygy.ca/jupyter/hub/user-redirect/git-pull?repo=https%3A%2F%2Fgithub.com%2Flheagy%2Fubc-jupyterdays-2020-widgets&urlpath=tree%2Fubc-jupyterdays-2020-widgets%2F&branch=master)
- or if you don't have a UBC CWL with full Syzygy access (a "guest" account will not be sufficient) you can use: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/lheagy/ubc-jupyterdays-2020-widgets/master?urlpath=lab)

There are three notebooks in this repository 
- [1-widgets-an-example.ipynb](https://mybinder.org/v2/gh/https%3A%2F%2Fmybinder.org%2Fv2%2Fgh%2Flheagy%2Fubc-jupyterdays-2020-widgets%2Fmaster/master?filepath=1-widgets-an-example.ipynb): A demo notebook that makes use of widgets to explore atmospheric CO2 data and linear models 
- [2-voila.ipynb](https://mybinder.org/v2/gh/lheagy/ubc-jupyterdays-2020-widgets/master?urlpath=voila%2Frender%2F2-voila.ipynb): A notebook based on the same CO2 data that is meant to be run as a voila dashboard
- [3-more-on-widgets.ipynb](https://mybinder.org/v2/gh/https%3A%2F%2Fmybinder.org%2Fv2%2Fgh%2Flheagy%2Fubc-jupyterdays-2020-widgets%2Fmaster/master?filepath=3-more-on-widgets.ipynb): A notebook with more details on widgets 

## Motivating Example: Atmospheric Carbon Dioxide

> _The climate emergency is one of the most pressing issues of our time. At this pivotal moment, the decisions and actions we take today will reverberate beyond our own borders and lifetimes._ -- [UBC Climate Emergency Engagement](https://climateemergency.ubc.ca/)

Carbon Dioxide (CO2) is a greenhouse gas, and significant contributor to the warming of the climate. It is an important input into climate models, which we use to make predictions about possible future climate scenarios, and sometimes to make policy decisions, including carbon taxes. 

**Question:** Based on historical CO2 data, can we estimate what CO2 concentrations will be in the future? 

### Learning Goals
- explore the idea of "learning": building a model from data that lets us make predictions 
- introduce the principles of linear regression, a simple, but powerful method for estimating a linear model of data
- explore the impact of outliers in data on the model 
- discuss the limitations of models

### Context

Scripps institute of Oceanography has a research station at Mauna Loa in Hawaii where they have been measuring atmospheric CO2 since 1958. The data we will focus on are the seasonally adjusted data. 

<img src="https://scrippsco2.ucsd.edu/assets/images/mlo_station_map.png" align="center">

**Data Source**

C. D. Keeling, S. C. Piper, R. B. Bacastow, M. Wahlen, T. P. Whorf, M. Heimann, and  H. A. Meijer, Exchanges of atmospheric CO2 and 13CO2 with the terrestrial biosphere and  oceans from 1978 to 2000.  I. Global aspects, SIO Reference Series, No. 01-06, Scripps  Institution of Oceanography, San Diego, 88 pages, 2001. https://scrippsco2.ucsd.edu/data/atmospheric_co2/primary_mlo_co2_record.html   

## Installing 

To run the notebooks locally, you will need to have python installed,
preferably through [anaconda](https://www.anaconda.com/download/). Please download 
Python 3.7 or greater. 

Once you have downloaded and installed anaconda, you can then clone this repository. 
From a command line (if you are on windows, please use the anaconda terminal that came with the installation)
run

```
git clone https://github.com/lheagy/ubc-jupyterdays-2020-widgets.git
```

Then `cd` into the `ubc-jupyterdays-2020-widgets` directory:

```
cd ubc-jupyterdays-2020-widgets
```

To setup your software environment, we recommend you use the provided conda environment

```
conda env create -f environment.yml
conda activate ubc-demo
```

You can then launch Jupyter

```
jupyter notebook
```

Jupyter will then launch in your web-browser.


## Jupyter widgets 

[Jupyter widgets](https://ipywidgets.readthedocs.io/en/latest/index.html) allow you to connect interactive controls such as slide bars and toggle buttons to your code. 

They can be used to create ["notebook apps"](https://jupyter4edu.github.io/jupyter-edu-book/catalogue.html#notebook-as-an-app) that abstract away details of the code and focus conversations on the role of parameters in a computation, or be a quick way to create a "Just-in-time-research-GUI" (GUI: graphical user interface) to explore results. 


### Getting started

Widgets can be [installed](https://ipywidgets.readthedocs.io/en/latest/user_install.html) with pip 

```
pip install ipywidgets
jupyter nbextension enable --py widgetsnbextension
```

or conda (which also enables the extension) 
```
conda install -c conda-forge ipywidgets
```

To enable the Jupyter Lab extension
```
jupyter labextension install @jupyter-widgets/jupyterlab-manager
```

For your first interaction with widgets, I recommend trying out `interact`. The `interact` function [`ipywidgets.interact`](https://ipywidgets.readthedocs.io/en/latest/examples/Using%20Interact.html) is a quick way to create user interface controls on your functions. At the most basic level, `interact` autogenerates controls for function arguments, and then calls the function with those arguments when you manipulate the controls interactively. To use `interact`, you need to define a function that you want to explore.

## Voilà Dashboards

> [Voilà](https://voila.readthedocs.io/en/stable/using.html#using-voila) turns Jupyter notebooks into standalone web applications.
> 
> Unlike the usual HTML-converted notebooks, each user connecting to the Voilà tornado application gets a dedicated Jupyter kernel which can execute the callbacks to changes in Jupyter interactive widgets.

- The [intro blog](https://blog.jupyter.org/and-voil%C3%A0-f6a2c08a4a93) provides an overview and resources for getting up and running with Voilà
- The [Voilà gallery](https://voila-gallery.org/) has a collection of examples built with Voilà and Jupyter widgets. 

If you are running on [binder](https://mybinder.org/v2/gh/lheagy/ubc-jupyterdays-2020-widgets/master), you can use the Voilà button! 

<img src="/img/voila-button.png" width=100% alt="voila-button">


### Getting Started

Voilà can be installed using `conda`

```
conda install -c conda-forge voila
```

or from PyPI
```
pip install voila
```

Once Voilà has been installed, 

- you can run it as a standalone server 
  
  ```
  voila notebook.ipynb
  ```
  
  
- or as a server extention by changing the url to `<url-of-my-server>/voila` (e.g. if you launched `jupyter lab` locally, and it was running at `http://localhost:8888/lab`, then then Voilà would be accessed at `http://localhost:8888/voila`.


- there is also a JupyterLab extention for previewing your dashboard
   
   ```
   jupyter labextension install @jupyter-voila/jupyterlab-preview
   ```

- by default, Voilà will strip out the source code from view. It can be displayed if the option `strip_sources` is set to False

## Acknowledgements

Many thanks to [Abby Azari](https://github.com/astro-abby) and [Fernando Pérez](https://github.com/fperez) for taking time to provide feedback on these notebooks! 
