# ubc-jupyterdays-2020-widgets
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/lheagy/ubc-jupyterdays-2020-widgets/master)
[![Syzygy](https://img.shields.io/badge/launch-syzygy-important)](https://ubc.syzygy.ca/jupyter/hub/user-redirect/git-pull?repo=https%3A%2F%2Fgithub.com%2Flheagy%2ubc-jupyterdays-2020-widgets&urlpath=tree%2Fubc-jupyterdays-2020-widgets%2F&branch=master)
[![Build Status](https://travis-ci.org/lheagy/ubc-jupyterdays-2020-widgets.svg?branch=master)](https://travis-ci.org/lheagy/ubc-jupyterdays-2020-widgets)

Here, we will use a motivating example that looks at CO2 data to demonstrate interactive computing with:
- [Jupyter Widgets](https://ipywidgets.readthedocs.io/en/latest/index.html) and 
- [Voilà dashboards](https://voila.readthedocs.io/en/latest/?badge=latest)

The example we follow is adapted from the [Intro-Jupyter tutorial from ICESat-2Hackweek](https://github.com/ICESAT-2HackWeek/intro-jupyter), which has contributions from: [Shane Grigsby (@espg)](https://github.com/espg), [Lindsey Heagy (@lheagy)](https://github.com/lheagy), [Yara Mohajerani (@yaramohajerani)](https://github.com/yaramohajerani), and [Fernando Pérez (@fperez)](https://github.com/fperez). 

## Notebooks
- UBC Students & Faculty can run on Syzygy: [![Syzygy](https://img.shields.io/badge/launch-syzygy-important)](https://ubc.syzygy.ca/jupyter/hub/user-redirect/git-pull?repo=https%3A%2F%2Fgithub.com%2Flheagy%2ubc-jupyterdays-2020-widgets&urlpath=tree%2Fubc-jupyterdays-2020-widgets%2F&branch=master)
- or if you don't have a UBC CWL with full Syzygy access (the "basic" accounts non-UBC personnel can use to register for the event aren't sufficient) you can use: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/lheagy/ubc-jupyterdays-2020-widgets/master)

## Motivating example: Climate Change

> _The climate emergency is one of the most pressing issues of our time. At this pivotal moment, the decisions and actions we take today will reverberate beyond our own borders and lifetimes._ -- [UBC Climate Emergency Engagement](https://climateemergency.ubc.ca/)

Carbon Dioxide (CO2) is a greenhouse gas, and significant contributor to the warming of the climate. It is an important input into climate models, which we use to make predictions about possible future climate scenarios, and sometimes to make policy decisions, including carbon taxes. 

**Question:** Based on historical CO2 data, can we estimate what CO2 concentrations will be in the future? 

## Learning Goals
- explore the idea of "learning": building a model from data that lets us make predictions 
- introduce the principles of linear regression, a simple, but powerful method for estimating a linear model of data
- explore the impact of outliers in data on the model 
- discuss the limitations of models

## Context

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

