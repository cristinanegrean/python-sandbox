# python-sandbox
Create a hello word gradle-py project using LinkedIn plugin: https://plugins.gradle.org/plugin/com.linkedin.python

Compare various Python packages for creating beautiful command line interfaces in a composable way with as little code as necessary:
* [fire](https://github.com/google/python-fire)
* [click](http://click.pocoo.org/5/)
* [argparse](https://docs.python.org/3/library/argparse.html)

[Existant comparison missing fire, listing docopt](https://realpython.com/blog/python/comparing-python-command-line-parsing-libraries-argparse-docopt-click)

### One-time project setup

As for the example project, you will need a setup.py in order to build the project; therefore, generate it (once) by calling:

```$ ./gradlew generateSetupPy```

### Creating a local PyPi repository that will be checked in *build.gradle*

1) [Download pivy repository](https://bintray.com/linkedin/maven/pivy-importer/0.6.14#files/com%2Flinkedin%2Fpygradle%2Fpivy-importer%2F0.6.14)

2) Have dependencies installed into path */tmp/repo/pypi*

```
$ java -jar ~/Development/pivy-importer-0.6.14-all.jar --repo /tmp/repo \
  click:6.7 \
  pip:9.0.1 \
  fire:0.1.2 \
  argparse:1.4.0 \
  docopt:0.6.2
```

### Build project

```
$ ./gradlew build
```

### Run

```
$ ./build/deployable/bin/hellopy
```
