## 1.1.0
### August 9th, 2021

CHANGES:

* Docker SDK for Python (```docker_sdk_for_python_install```) is now disabled by default.
* Added systemd settings support - ```docker_service_enabled``` and ```docker_service_state```.
* Moved from generic ```package``` module to OS specific - ```apt``` and ```yum / dnf```.

BUG FIXES:

* Fix handler name to avoid error when using ```docker_daemon_config``` variable.
* Fixed repo file name when using RHEL.
* Checked and fixed YAML syntax with ```yamllint```.

## 1.0.0
### November 17th, 2020

CHANGES:

* Initial release! 🎉