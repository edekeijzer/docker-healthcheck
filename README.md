# docker-healthcheck
Simple little framework to simplify health checks in Docker

## Usage
* Copy _healthcheck_ to your container
* Create a directory (default _/etc/healthcheck.d_) in your container
* Create simple healthcheck scripts in this directory
  * A non-zero exit code will trigger failure of the check
  * STDOUT will be discarded
  * STDERR can optionally be written to healthcheck output, but keep it brief
* Add HEALTHCHECK CMD to your Dockerfile

## Caveats
* Specifying the script directory and verbose printing of error messages are currently positional parameters - directory first, verbosity second

## To-Do
- [ ] Named parameters instead of positional
- [ ] Read options from config file instead of command line parameters
