# apt-cacher-ng Docker Container

This repository provides a Docker container for `apt-cacher-ng` with a specific basic configuration for repository usage.

## Table of Contents

- [apt-cacher-ng Docker Container](#apt-cacher-ng-docker-container)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Features](#features)
  - [Installation](#installation)
  - [Usage](#usage)
  - [Configuration](#configuration)
  - [Contributing](#contributing)
  - [License](#license)

## Introduction

`apt-cacher-ng` is a caching proxy for Debian-based distributions. This Docker container comes pre-configured with specific repositories to streamline your setup process.

## Features

- Pre-configured repository settings
- Easy to deploy with Docker
- Reduces bandwidth usage and speeds up package installations

## Installation

To build and run the Docker container, use the following commands:

```sh
docker build -t apt-cacher-ng .
docker run -d -p 3142:3142 --name apt-cacher-ng apt-cacher-ng
```

## Usage

Point your `apt` configuration to use the `apt-cacher-ng` proxy. Add the following line to your `/etc/apt/apt.conf.d/01proxy` file:

```sh
Acquire::http { Proxy "http://<your-docker-host-ip>:3142"; };
```

## Configuration

The container comes with a basic configuration. You can customize it by editing the `acng.conf` file and rebuilding the Docker image.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.