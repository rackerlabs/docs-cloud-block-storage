# Rackspace Cloud Block Storage API documentation

[![Build Status](https://travis-ci.org/rackerlabs/docs-cloud-block-storage.svg?branch=master)](https://travis-ci.org/rackerlabs/docs-cloud-block-storage)


## Purpose

This GitHub repository contains the source files for the following Rackspace Cloud Block Storage API documentation:

* [Getting started](https://developer.rackspace.com/docs/cloud-block-storage/v1/getting-started/)
* [General API information](https://developer.rackspace.com/docs/cloud-block-storage/v1/general-api-info/)
* [API reference](https://developer.rackspace.com/docs/cloud-block-storage/v1/api-reference/)
* [Release notes](https://developer.rackspace.com/docs/cloud-block-storage/v1/release-notes/)




## Contributing

Contributions are welcome!

* To suggest changes or report a problem, submit an [issue](https://github.com/rackerlabs/docs-cloud-block-storage/issues).

* To make changes to a project, create your own fork of the repository. Then, submit a [pull
request](https://github.com/rackerlabs/docs-cloud-block-storage/compare?expand=1) to have your changes reviewed
and merged into the master branch as appropriate.

To contribute content, all you need is an editor and a
basic understanding of the project layout and [reStructuredText](http://sphinx-doc.org/rest.html) syntax.

You can use the GitHub editor or any text editor to work with documentation source files. For quick syntax checking, try the
[Online restructuredText editor](http://rst.ninjs.org/).

**Note:** If you want to build the project, you need to install the [Sphinx documentation generator](http://www.sphinx-doc.org/en/stable/install.html).

## Source format

The Rackspace developer documentation is developed and built using the [Python Sphinx documentation generator](http://sphinx-doc.org/). Content is
written in [reStructuredText](http://sphinx-doc.org/rest.html), the markup syntax and parser component of
[Python Docutils](http://docutils.sourceforge.net/index.html).

The repository includes the documentation source files,
Sphinx configuration and build files, as well any required Sphinx
extensions and build tools.

## Structure

Source files for the Sphinx documentation project are in the ``rst/dev-guide`` directory. Here are the key files that define
the Sphinx project and content architecture for the documentation:

Content | File
--- | ---
|Sphinx documentation configuration file| [conf.py](https://github.com/rackerlabs/docs-cloud-block-storage/blob/master/api-docs/conf.py) (Typically, this file does not require changes.)
|Index page for the main content structure| [index.rst](https://github.com/rackerlabs/docs-cloud-block-storage/blob/master/api-docs/index.rst)
|Getting started|[getting-started folder](https://github.com/rackerlabs/docs-cloud-block-storage/tree/master/api-docs/getting-started)
|General API information|[general-api-info folder](https://github.com/rackerlabs/docs-cloud-block-storage/tree/master/api-docs/general-api-info)
|API reference|[api-reference folder](https://github.com/rackerlabs/docs-cloud-block-storage/tree/master/api-docs/api-reference)
|API reference methods, including code samples|[api-reference/methods](https://github.com/rackerlabs/docs-cloud-block-storage/tree/master/api-docs/api-reference/methods)
|Release notes |[release-notes folder](https://github.com/rackerlabs/docs-cloud-block-storage/tree/master/api-docs/release-notes)

|**make.bat**|Windows build script
|**Makefile**| Linux and OS X build

### Support and feedback

If you find a problem, open a GitHub [issue](https://github.com/rackerlabs/docs-cloud-block-storage/issues).

If you need additional assistance, contact us at [devdoc@rackspace.com](mailto:devdoc@rackspace.com).
