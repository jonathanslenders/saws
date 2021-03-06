Release Checklist
=================

A. Run unit tests

    $ tox

B. Run code checks

    $ scripts/run_code_checks.sh

C. Run manual smoke tests on Mac, Ubuntu, Windows*

D. Update and review `README.rst`

    $ scripts/create_readme_rst.sh

E. Update and review `Sphinx` docs

    $ python setup.py build_sphinx

F. Push changes

G. Review Travis, Codecov, and Gemnasium

H. Start a new release branch

    $ git flow release start x.y.z

I. Increment the version number in `saws/__init__.py`

J. Update and review `CHANGELOG`

    $ scripts/create_changelog.sh

K. Commit the changes

L. Finish the release branch

    $ git flow release finish 'x.y.z'

M. Input a tag

    $ vx.y.z

N. Push tagged release to develop and master

O. Temporarily remove README before pushing to PyPi  # TODO

P. Register package with PyPi

    $ python setup.py register -r pypi

Q. Upload to PyPi

    $ python setup.py sdist upload -r pypi

R. Upload Sphinx docs to PyPi

    $ python setup.py upload_sphinx

S. Review newly released package from PyPi

T. Install and run manual smoke tests on Mac, Ubuntu, Windows*

U. Restore README  # TODO

V. Rebuild Readthedocs at https://readthedocs.org/projects/saws/builds/

## Smoke Tests

Run the following on Python 2.7 and Python 3.4:

* Craete a new `virtualenv`
* Pip install `SAWS` into new `virtualenv`
* Run `SAWS`
* Empty cache
* Check resource load from cache
* Force refresh of resources
* Toggle toolbar options
* Verify toolbar options are saved across sessions
* Commands
    * Blank
    * aws
    * aws elb
    * aws s3api get-bucket-acl --bucket
    * aws ec2 describe-instances --instance-ids
    * aws ecls
    * aws ectagk
    * aws ectagv
    * aws ecstate
    * aws s3 ls s3:
    * aws s3 ls docs
* Run specialized tests based on code changes
