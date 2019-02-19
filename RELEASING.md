# Release Checklist for PyPlanet core + contrib apps.

## Main Release

* [ ] Open a release ticket with the version and the release notes in a short summary.
* [ ] Develop and prepare release in ``master`` branch.
* [ ] Check the Travis CI build status of the ``master`` branch.
* [ ] Make sure we update the version number according to Semver 2.0.0.
* [ ] Update `CHANGELOG.rst`.
* [ ] Bump version with `bumpversion --new-version 0.6.0 final` (this will commit the changes directly).
* [ ] (Only when manually updating, not using bumpversion) Update documentation version `conf.py` and `__init__.py` in PyPlanet root folder.
* [ ] Run build commands with `make build` and test the cli with pip installation.
* [ ] Create new branch for the big releases (if major/minor update, not for bugfix):
```
    $ git checkout -b release/2.9.x
    $ git tag 2.9.0
    $ git push --all
    $ git push --tags
```
* [ ] Create and upload source distributions e.g.:
```
    $ make build
    $ make publish
```
* [ ] Create/update release notes on Github releases page.
