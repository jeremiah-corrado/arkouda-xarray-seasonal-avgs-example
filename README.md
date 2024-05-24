# arkouda-xarray-seasonal-avgs-example

An example of how to use [Arkouda](https://github.com/Bears-R-Us/arkouda)'s [Array-API module](https://bears-r-us.github.io/arkouda/autoapi/arkouda/array_api/index.html) as the backend for [XArray](https://docs.xarray.dev/en/stable/).

Follows [this](https://docs.xarray.dev/en/stable/examples/monthly-means.html) example from the XArray Gallery.

## instructions

To run the example, make sure you have a local installation of [Chapel](https://chapel-lang.org/download.html) and [Arkouda](https://bears-r-us.github.io/arkouda/setup/install_menu.html), and then follow these instructions to set up Arkouda and your python environment.

1. clone this repo
2. create conda enviroment ...
3. install XArray and arkouda-xarray ...
4. install your local arkouda lib
   * `pip install -e .`
5. build the arkouda server to support multidimensional arrays
   * edit `serverConfig.json` to have a max array rank of 3
   * `ARKOUDA_CONFIG_FILE=ArrayAPIServerModules.cfg make`
6. start the arkouda server
   * `./arkouda_server` (`-nl 4` if multilocale)
7. run the jupyter notebook
    * should see execution of server commands in logs ...
