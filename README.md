# arkouda-xarray-seasonal-avgs-example

An example of how to use [Arkouda](https://github.com/Bears-R-Us/arkouda)'s [Array-API module](https://bears-r-us.github.io/arkouda/autoapi/arkouda/array_api/index.html) as the backend for [XArray](https://docs.xarray.dev/en/stable/).

Follows [this](https://docs.xarray.dev/en/stable/examples/monthly-means.html) example from the XArray Gallery.

## Dependencies

* [Chapel](https://chapel-lang.org/download.html)
* [Arkouda](https://bears-r-us.github.io/arkouda/setup/install_menu.html)
* Anaconda

## Instructions

After completing the installation instructions for Chapel and Arkouda, go through the following steps to get the Jupyter notebook in this repo running:

1. clone and cd into this repo

2. create and activate the conda environment to install Xarray and set up some of Arkouda and XArray's dependencies
    * `conda env create -f arkouda-xarray-env.yaml`
    * `conda activate arkouda-xarray-env`

3. install the `arkouda-xarray` package into the environment
    * clone the [repo](https://github.com/jeremiah-corrado/arkouda-xarray)
    * `cd` into `arkouda-xarray` and `pip install .`

4. install Arkouda into the environment
    * `cd` into your local Arkouda directory
    * `pip install .`

5. build the Arkouda server to support multidimensional arrays
    * in your local Arkouda directory, edit `serverConfig.json`, setting `"max_array_dims": 3`
   * build the server for Array API compatibility: `ARKOUDA_CONFIG_FILE=ArrayAPIServerModules.cfg make` (this will take some time)

6. start the Arkouda server
   * `./arkouda_server`
   * (or `./arkouda_server -nl4` if Chapel is configured for multinode builds)

7. run the Jupyter notebook
    * as it runs, you should see the server executing commands in your terminal

8. stop the Arkouda server
