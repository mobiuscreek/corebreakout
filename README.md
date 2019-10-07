# CoreBreakout

## Overview

`corebreakout` is a Python package built around [matterport/Mask\_RCNN](https://github.com/matterport/Mask_RCNN) for the segmentation and depth alignment of geological core images. It also provides the `CoreColumn` data structure for the saving, loading, and visualization of core image data.

### TODO

- Move `CorePlotter` or parts of it into this package (check tick generation though -- make sure it works with `mode='collapse'`)

- Write tutorials: one for building/training models, one for performing inference and processing datasets

- Clean up `scripts/` and `notebooks` directories

- Finishing writing `pytest` files


## Target Platform

This package was developed and tested under Linux (Ubuntu, PopOS). It may work on other platforms, but probably requires adjustment of some configuration file parameters found at [corebreakout/defaults.py] (e.g., file system conventions for Windows).


## Requirements

The following Python packages are required:

- `numpy`
- `matplotlib`
- `scikit-image`
- `tensorflow`
- `mrcnn` via [matterport/Mask\_RCNN](https://github.com/matterport/Mask_RCNN)

The installation should check for and install `numpy`, `matplotlib`, and `scikit-image`.

The user is responsible for installing `tensorflow`, due to the ambiguity between `tensorflow` and `tensorflow-gpu`. We highly recommend the latter for building new models, although it may be possible to perform inference on CPU.

Using `tensorflow-gpu` is very much recommended.


## Installation

**Download:**

```
$ git clone https://github.com/rgmyr/corebreakout.git
$ cd corebreakout
```

Then install the package using **`pip`**. Develop mode installation (`-e`) is recommended, since many users will want to change some parameters to suit their particular dataset without having to reinstall afterward:
```
$ pip install -e .
```

## Data Assets

In order to run tests, or perform inference without training a new model, you will need to download the data.

Run tests with `pytest`

## Tutorial

# Using new datasets

Third party tools are necessary for labeling new training images. There is built-in support for the default polygonal JSON annotation format of the [wkentaro/labelme](https://github.com/wkentaro/labelme) graphical image annotation tool, but any instance segmentation annotation format would be workable if the user is willing to write their own subclass of `mrcnn.utils.Dataset`.

For more details about `Dataset`s, see: [docs/creating_datasets.md]

# Development and Community Guidelines

## Submit and Issue

## Contributing

### Testing
