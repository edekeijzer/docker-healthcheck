# docker-healthcheck
Simple little framework to simplify health checks in Docker

## Usage
* Copy _healthcheck_ to your container
* Create a directory (default _/etc/healthcheck.d_) in your container
* Create simple healthcheck scripts in this directory
  * A non-zero exit code will trigger failure of the check
  * STDOUT will be discarded
  * STDERR can optionally be written to healthcheck output by specifying _verbose_, but keep it brief.
* Add HEALTHCHECK CMD to your Dockerfile

## Example
For a generic TCP port check, use _netcat_ (available by default in Alpine through Busybox) and use the command _nc -z localhost <port>_ in the healthcheck script

## To-Do
- [x] Named parameters instead of positional
- [x] Read options from config file instead of command line parameters
- [ ] Long option names
