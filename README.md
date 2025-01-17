[![Tests](https://github.com/JiscSD/ckanext-ukdstheme/workflows/Tests/badge.svg?branch=main)](https://github.com/JiscSD/ckanext-ukdstheme/actions)

# Cookie Banner Plugin for CKAN

This is the cookie banner plugin for UKDS CKAN instance. 
It includes the necessary JavaScript files to apply the civic cookie banner.

## Features included
1. Cookie Banner Displayed
2. Configured correct text
3. Link to the UKDS Privacy Policy
4. Ability to change appearance and behaviour of the cookie banner


## Requirements

This plugin is developed and tested on CKAN version 2.9 & 2.11

Compatibility with core CKAN versions:

| CKAN version    | Compatible? |
|-----------------|-------------|
| 2.9             | yes         |
| 2.10            | not tested  |
| 2.11            | yes    	    |


## Installation

To install ckanext-cookie_banner:

1. Activate your CKAN virtual environment, for example:
```
     . /usr/lib/ckan/default/bin/activate
```
2. Clone the source and install it on the virtualenv
```
	cd /usr/lib/ckan/default/src
    python3 -m pip install -e git+https://github.com/JiscSD/ckanext-cookie-banner.git#egg=ckanext-cookie-banner
	
	then reset the permissions for the new ckanext-cookie-banner directory to 'ckan'
```
3. Add `cookie_banner` to the `ckan.plugins` setting in your CKAN
   config file (by default the config file is located at
   `/etc/ckan/default/ckan.ini`).

4. Restart CKAN. For example if you've deployed CKAN with Apache on Ubuntu:
```
     sudo service apache2 reload
```
or if the server is on AWS, called
```
     sudo systemctl restart nginx 
```

## Updating to a new version

To update ckanext-cookie_banner:

1. Activate your CKAN virtual environment, for example:
```
     . /usr/lib/ckan/default/bin/activate
```
2. pull the latest version then install it on the virtualenv
```
	cd /usr/lib/ckan/default/src/ckanext-cookie-banner
    git pull
    pip install -e .
	
	then reset the permissions for the ckanext-cookie-banner directory to 'ckan'
```

3. Restart CKAN. For example if you've deployed CKAN with Apache on Ubuntu:
```
     sudo service apache2 reload
```
or if the server is on AWS, called
```
     sudo reboot now 
```

## Config settings

None at present

## Developer installation

To install ckanext-cookie_banner for development, activate your CKAN virtualenv and
do:

    python3 -m pip install -e git+https://github.com/JiscSD/ckanext-cookie-banner.git#egg=ckanext-cookie-banner
    cd ckanext-cookie-banner
    python3 setup.py develop
    python3 -m pip install -r dev-requirements.txt


## Tests

To run the tests, do:

    pytest --ckan-ini=test.ini


## Releasing a new version of ckanext-cookie_banner

If ckanext-cookie_banner should be available on PyPI you can follow these steps to publish a new version:

1. Update the version number in the `setup.py` file. See [PEP 440](http://legacy.python.org/dev/peps/pep-0440/#public-version-identifiers) for how to choose version numbers.

2. Make sure you have the latest version of necessary packages:

    pip install --upgrade setuptools wheel twine

3. Create a source and binary distributions of the new version:

       python setup.py sdist bdist_wheel && twine check dist/*

   Fix any errors you get.

4. Upload the source distribution to PyPI:

       twine upload dist/*

5. Commit any outstanding changes:

       git commit -a
       git push

6. Tag the new release of the project on GitHub with the version number from
   the `setup.py` file. For example if the version number in `setup.py` is
   0.0.1 then do:

       git tag 0.0.1
       git push --tags

## License

[Unlicense](https://unlicense.org/)
