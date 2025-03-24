# LaTeX Workshop Docker Image

This repository contains a Docker image designed for use with the **LaTeX Workshop** extension in VS Code. It provides a pre-configured LaTeX environment to compile `.tex` files seamlessly.

## Features

- To be used with [Latex Workshop](https://github.com/James-Yu/LaTeX-Workshop)
- Multi-platform support (`linux/amd64`, `linux/arm64`)
- Pre-installed LaTeX packages for a complete development setup
- Optimized for integration with LaTeX Workshop in VS Code

## Usage

### Pull the Image

To use this image, pull it from Docker Hub:

```sh
docker pull hieumdd/latex-workshop:latest
```

### Run a Container

You can run a container with the following command:

```sh
docker run --rm -v $(pwd):/workspace -w /workspace hieumdd/latex-workshop pdflatex main.tex
```

Replace `main.tex` with your actual LaTeX file.

## Building the Image Locally

If you want to build the image manually, clone this repository and run:

```sh
docker buildx build --platform linux/amd64,linux/arm64 -t hieumdd/latex-workshop:latest .
```

## GitHub Actions Workflow

This repository includes a GitHub Actions workflow to automate the build and push process to Docker Hub.

### Workflow Triggers

- Push to `master` branch
- Manual trigger via GitHub Actions UI

### Build and Push Process

1. Sets up QEMU and Docker Buildx for multi-platform builds
2. Logs in to Docker Hub using GitHub secrets
3. Builds and pushes the image for `linux/amd64` and `linux/arm64` architectures
4. Tags the image as `latest` and with the current commit SHA

## Contributing

Feel free to open issues or pull requests to improve this image.

## License

This project is licensed under the GNU General Public License v3.0.
