# Guidance for evaluating pi0-fast on LIBERO-plus
## Installation
Please follow the installation guidance in [LIBERO-plus](https://github.com/sylvestf/LIBERO-plus) as below
>The usage of this project is identical to LIBERO. Simply replace the originally installed LIBERO repository with our repository without modifying your code.
>```
>   # Clone our repository
>   git clone https://github.com/sylvestf/LIBERO-plus.git
>   cd LIBERO-plus
>```
>If you have LIBERO installed, please uninstall or remove it first. Please verify if the repo path in the following configuration file needs to be updated to path_to_liberoplus_repo. Here are the default paths for the configuration files: `/root/.libero/config.yaml.` You can check your libero_config_path at `path_to_your_LIBERO_repo/libero/libero/__init__.py`.
>Then install our new LIBERO repository
>```
>   # Install the new LIBERO package
>   pip install -e .
>
>   # New dependencies installed on top of LIBERO
>   apt install libexpat1
>   apt install libfontconfig1-dev
>   apt install libpython3-stdlib
>   apt-get install libmagickwand-dev
>   pip install -r extra_requirements.txt
>```
Make sure that your LIBERO-plus path is correct, you can check it with `pip show libero`
And then install the openpi dependencies following the guidance in [Openpi](https://github.com/Physical-Intelligence/openpi) as below
>When cloning this repo, make sure to update submodules:
>```
>   git clone --recurse-submodules git@github.com:Physical-Intelligence/openpi.git
>
>   # Or if you already cloned the repo:
>   git submodule update --init --recursive
>```
>We use [uv](https://docs.astral.sh/uv/) to manage Python dependencies. See the [uv installation instructions](https://docs.astral.sh/uv/getting-started/installation/) to set it up. Once uv is installed, run the following to set up the environment:
>```
>   GIT_LFS_SKIP_SMUDGE=1 uv sync
>   GIT_LFS_SKIP_SMUDGE=1 uv pip install -e .
>```
>NOTE: GIT_LFS_SKIP_SMUDGE=1 is needed to pull LeRobot as a dependency.
>
>Docker: As an alternative to uv installation, we provide instructions for installing openpi using Docker. If you encounter issues with your system setup, consider using Docker to simplify installation. See [Docker Setup](https://github.com/Physical-Intelligence/openpi/blob/main/docs/docker.md) for more details.
## Run evaluation
Please refer to the [openpi-libero](https://github.com/Physical-Intelligence/openpi/tree/main/examples/libero) for detailed instructions, and here we provide a simple example for evaluating pi0-fast using [without docker method](https://github.com/Physical-Intelligence/openpi/tree/main/examples/libero#without-docker-not-recommended)
Note that the openpi official has released new models so their repo files have been revised to new models, here I use the pi0-fast model to launch the server, 
