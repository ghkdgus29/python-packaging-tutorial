# Packaging Python Projects (Test Pypi)

This is a simple example package.  <br>
Based on the packaging tutorial from the [official Python docs](https://packaging.python.org/en/latest/tutorials/packaging-projects/).


## Deploy 

```bash
python3 -m venv .venv 
source .venv/bin/activate
```
> create & activate virtual env 

<br>

```bash
pip install build
```
> install build package

<br>

```bash
python3 -m build
```
> package build 

<br>

```bash
pip install twine
```
> install twine package

<br>

```bash
python3 -m twine upload --repository testpypi dist/* 
```
> upload built package to testpypi

```
Enter your API token:
Uploading example_package_hyun0429-0.0.1-py3-none-any.whl
100% ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 5.6/5.6 kB • 00:00 • ?
Uploading example_package_hyun0429-0.0.1.tar.gz
100% ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 5.0/5.0 kB • 00:00 • ?

View at:
https://test.pypi.org/project/example-package-hyun0429/0.0.1/
```

<br>

## Install
```bash
pip install --index-url https://test.pypi.org/simple/ --no-deps example-package-hyun0429
```
> install my sample package 

<br>

```bash
python3
>>> from example_package_hyun import example
>>> example.add_one(29)
30
```
> actually, directory name is example_package_hyun, not example_package_hyun0429 <br>
> Matching names seems like a better idea. 

## Cautions
Keep in mind that this tutorial showed you how to upload your package to Test PyPI, which isn’t a permanent storage. The Test system occasionally deletes packages and accounts. Uploading a package to PyPI is subtly different.

