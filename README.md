
# Lambda Layer Generator for python

This project provides a simple and efficient way to generate AWS Lambda layers for Python dependencies.

## Overview

AWS Lambda layers allow you to package and share common code dependencies across multiple Lambda functions. This project automates the process of creating Lambda layers by using Docker to ensure compatibility with the Lambda execution environment.

## Features

- Supports Python 
- Uses Docker to ensure compatibility with AWS Lambda environment
- Automatically processes multiple layers
- Generates zip files ready for upload to AWS Lambda

## Prerequisites

- Docker
- Bash shell
- AWS CLI (for uploading layers to AWS)

## Project Structure

lambda_layer/

├── build.sh

├── layers/

│ ├── layer1/

│ │ └── requirements.txt

│ ├── layer2/

│ │ └── requirements.txt

│ └── ...

└── packages/

├── layer1.zip

├── layer2.zip

└── ...


## Usage

1. Create a directory for each layer you want to build inside the `layers/` directory.

2. Place a `requirements.txt` file in each layer directory with the desired Python packages.
3. Run the build script:

`./build.sh`


4. The script will process each layer and create corresponding zip files in the `packages/` directory.

## How it works

The `build.sh` script:

1. Sets up the Python version and creates a `packages/` directory.
2. Iterates through each subdirectory in the `layers/` folder.
3. Uses a Docker container to install the requirements in a Lambda-compatible environment.
4. Zips the installed packages into a layer-specific zip file.

## Customization

- To change the Python version, modify the `PYTHON_VERSION` variable in `build.sh`.
- Add or remove layer directories in the `layers/` folder as needed.


