# `hello-vpp-py` Sample

This sample shows how to use the oneAPI Video Processing Library (oneVPL) to
perform simple video processing using using Python APIs.

Please note: the preview Python API and its samples are no longer under development.
They are not validated and may be removed in the future.

| Optimized for       | Description
|-------------------- | ----------------------------------------
| OS                  | Ubuntu* 20.04; Windows* 10
| Hardware            | Compatible with Intel® oneAPI Video Processing Library(oneVPL) GPU implementation, which can be found at https://github.com/oneapi-src/oneVPL-intel-gpu 
| Software            | Intel® oneAPI Video Processing Library(oneVPL) CPU implementation
| What You Will Learn | How to use oneVPL to resize and change color format of a raw video file
| Time to Complete    | 5 minutes

## Purpose

This sample is a Python script that takes a file containing a raw
format video elementary stream as an argument. Using oneVPL, the application
processes it and writes the resized output to `out.raw` in BGRA raw video format.

Native raw frame input format: CPU=I420, GPU=NV12.

| Configuration     | Default setting
| ----------------- | ----------------------------------
| Target device     | CPU
| Input format      | I420
| Output format     | BGRA raw video elementary stream
| Output resolution | 640 x 480

## License

This code sample is licensed under MIT license.


## Building the `hello-vpp-py` Program

Python samples do not need to be built, however you must ensure that the
Python binding is installed, and that you are using a compatible version of Python.

See [Preview Documentation](https://software.intel.com/content/www/us/en/develop/articles/onevpl-preview-examples.html)
for details.

### Installing a compatible version of Python
This example uses Python 3.x.

The oneVPL Python Binding is built against a specific version of Python.

The version of python targeted depends on the version available on the system
where the binding is built, so in most cases if you have built the binding
for yourself the versions will match.

Many prebuilt versions of the oneVPL Python Binding target Python 3.7
which may need to be installed.

For Ubuntu 20.04, install with ``sudo apt install python3.7``.

For Windows, install latest Python 3 release from https://www.python.org/downloads/windows/

### Setting up python binding (quick reference)

The Python binding is shipped in the folder ``<oneVPL>/lib/python``. The file will be
named ``pyvpl.<pytype><python-version>-<os>.<so or pyd>``.

On Windows:

1. Ensure that the Python install you are using matches the python-version in the binding file's name.
2. Copy ``<oneVPL>/lib/python/pyvpl.*`` to ``<oneVPL>/bin/``.
3. Add ``<oneVPL>/bin`` to the ``PYTHONPATH`` environment variable.

On Linux:

1. Ensure that the Python install you are using matches the python-version in the binding file's name.
2. Copy ``<oneVPL>/lib/python/pyvpl.*`` to ``<oneVPL>/lib/``.  Note: this is so pyvpl and dispatcher library can be in the same directory.
3. Add ``<oneVPL>/lib`` to the ``PYTHONPATH`` environment variable.  

## Running the Sample

Note: Please ensure you run these samples with a version of Python matching the binding installed (as described above).
If versions do not match the binding will not be loaded into the Python environment.

The following examples assume Python 3.7

On Windows:

The sample writes its output in the current directory. Please ensure the current directory is writable when running this sample.

```
py -3.7 hello-vpp-py\hello-vpp.py <examples path>\content\cars_320x240.i420 320 240
```

On Linux:

```
python3.7 hello-vpp-py/hello-vpp.py <examples path>\content\cars_320x240.i420 320 240
```
