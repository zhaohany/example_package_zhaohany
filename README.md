https://packaging.python.org/en/latest/tutorials/packaging-projects/

1. strutures:make sure have _init_.py in src -> project_name
2. add LICENSE, README.MD, tests folder and pyproject.toml
3. in pyproject.toml, add based on the backend package using: Hatchling,setuptools, Flit, PDM
4. add requirement:requires is a list of packages that are needed to build your package. You don’t need to install them; build frontends like pip will install them automatically in a temporary, isolated virtual environment for use during the build process.
5. build-backend is the name of the Python object that frontends will use to perform the build.
6.contunue config metas
7. source distribution(sdist) or build distribution(wheel)
By default, pip will always attempt to install a wheel unless there is no whl file for your operating system, at which point pip will attempt to build the wheel from the sdist (note that this can fail if you don't have the appropriate resources and requirements on your system).

sudo apt install python3-pip
pip3 install build

apt install python3.10-venv

python3 -m build --sdist /home/yzh/Desktop/dl/example_package_zhaohany

python3 -m build --wheel /home/yzh/Desktop/dl/example_package_zhaohany

sudo apt install twine
twine upload dist/example_package_zhaohany-0.0.1.tar.gz dist/example_package_zhaohany-0.0.1-py3-none-any.whl

api token issue
HTTPError: 401 Unauthorized from https://upload.pypi.org/legacy/
User zhaohany has two factor auth enabled, an API Token or Trusted Publisher must be used to upload in place of password.