# Data Visualization including aggregation, interactive visualizations, and geospatial analysis.
This platform aims to offer one-click service for people to buy properties and then rent them. It utilizes data visualization superpowers, including aggregation, interactive visualizations, and geospatial analysis, to find properties in the San Francisco market that are viable investment opportunities.

---
## Technologies
- [Anaconda](https://www.anaconda.com/products/individual) - Pandas is included in Anaconda distribution and Conda package manager to manage Python environments.
- [Jupyter Lab](https://jupyter.org/) - web-based user interface designed for data analysis. It lets you write, run, and review the results in Python programs (all in a single integrated development environment (IDE).
- [Plotly Express documentation page](https://plotly.com/python/scattermapbox/#mapbox-access-token-and-base-map-configurationPlotly) - Express is the easy-to-use, high-level interface to Plotly, which operates on a variety of types of data and produces easy-to-style figures.
- [Mapbox Maps services](https://docs.mapbox.com/) - Maps and location for developers. Precise location data and powerful developer tools to change the way we navigate the world.
- [Mapbox API integration with the Plotly Express libray](https://plotly.com/python/scattermapbox/) - that enables the visualization of geographically based data in a scatter plot.

---
## Installation Guide

Install the PyViz Ecosystem

PyViz is a Python visualization package that provides a single platform for accessing multiple visualization libraries. Two of these libraries are Plotly Express and hvPlot, which you’ll use during this module.

To install PyViz and its dependencies in your Conda dev environment, complete the following steps:

From your terminal, log in to your Conda dev environment.

Install the PyViz packages by using the conda install command as follows:

```
conda install -c plotly plotly=4.13.
conda install -c pyviz hvplot

```

PyViz also requires a specific version of NodeJS. To install the correct version, run the following command:

```
conda install -c conda-forge nodejs=12

```

Confirm the installation of all the PyViz packages by running the following commands:

```
 conda list plotly
 conda list hvplot
 conda list nodejs
 
```

With the python-dotenv library, you can read key-value pairs from an environment file (.env) and add them as environment variables.
To install this library, run the following command in your terminal:

```
pip install python-dotenv

```

Install the JupyterLab Dependencies
For your PyViz plots to render in JupyterLab, you also need to install a specific version of JupyterLab, as well as the JupyterLab extensions. To install the required JupyterLab version and the extensions for PyViz and Plotly Express, run the following commands in the terminal:

```
conda install -c conda-forge jupyterlab=2
jupyter labextension install jupyterlab-plotly@4.13.0 --no-build
jupyter labextension install @jupyter-widgets/jupyterlab-manager plotlywidget@4.13.0 --no-build
jupyter labextension install @pyviz/jupyterlab_pyviz --no-build

```

Now that you’ve installed the extensions in your Conda dev environment, you need to apply, or build, them to the JupyterLab software. To do so, run the following code (this process might take a few minutes):

```
jupyter lab build

```

Set Up the Mapbox API
To use the Mapbox API in this module, you need to register for a public Mapbox API access token. To set up and store your access token, follow the instructions in this section. You can also find detailed instructions on the Plotly Express documentation page (https://plotly.com/python/scattermapbox/#mapbox-access-token-and-base-map-configuration).

The access token that you register for corresponds to an API key. That is, you use the Mapbox access token to access the Mapbox API. You first store the access token in an environment file (.env). You then import that file into the notebook where you make your API call to Mapbox and create the plot.

You’ll use the Mapbox API access token together with an environment file (.env) to import it into the notebooks where you’ll create your visualizations. You can store your Mapbox API access token like this:

```
API Keys

Mapbox
MAPBOX_API_ACCESS_TOKEN="Your Mapbox API access token here”

```

---

## Usage

Using Plotly Express, created a scatter_mapbox for the all_neighborhoods_df DataFrame. 


```
# Using Plotly Express, create a scatter_mapbox for the all_neighborhoods_df DataFrame.
# Set the `size` parameter to “sale_price_sqr_foot”.
# Set the `color` parameter to “gross_rent”.
# Set the `size_max` parameter to “25”.
# Set the `zoom` parameter to “11”.

fig = px.scatter_mapbox(
    all_neighborhoods_df,
    lat="Lat",
    lon="Lon",
    size="sale_price_sqr_foot",
    color="gross_rent",
    size_max=25,
    zoom=11
)

fig.show()

```

## Contributors

Created by Bina Jariwala

---

## License

None

---
