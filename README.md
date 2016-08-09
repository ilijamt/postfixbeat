# Postfixbeat

Welcome to Postfixbeat.

Ensure that this folder is at the following location:
`${GOPATH}/github.com/ilijamt`

## Getting Started with Postfixbeat

### Requirements

* [Golang](https://golang.org/dl/) 1.6.2
* [Glide](https://glide.sh/)

### Dependencies

To download all dependencies run the command below. This will generate all of them
in a local directory called vendor.

```
glide install
```

### Build

To build the binary for Postfixbeat run the command below. This will generate a binary
in the same directory with the name postfixbeat.

```
make
```


### Run

To run Postfixbeat with debugging output enabled, run:

```
./postfixbeat -c postfixbeat.yml -e -d "*"
```


### Test

To test Postfixbeat, run the following command:

```
make testsuite
```

alternatively:
```
make unit-tests
make system-tests
make integration-tests
make coverage-report
```

The test coverage is reported in the folder `./build/coverage/`

### Update

Each beat has a template for the mapping in elasticsearch and a documentation for the fields
which is automatically generated based on `etc/fields.yml`.
To generate etc/postfixbeat.template.json and etc/postfixbeat.asciidoc

```
make update
```


### Cleanup

To clean  Postfixbeat source code, run the following commands:

```
make fmt
make simplify
```

To clean up the build directory and generated artifacts, run:

```
make clean
```


### Clone

To clone Postfixbeat from the git repository, run the following commands:

```
mkdir -p ${GOPATH}/github.com/ilijamt
cd ${GOPATH}/github.com/ilijamt
git clone https://github.com/ilijamt/postfixbeat
```


For further development, check out the [beat developer guide](https://www.elastic.co/guide/en/beats/libbeat/current/new-beat.html).


## Packaging

The beat frameworks provides tools to crosscompile and package your beat for different platforms. This requires [docker](https://www.docker.com/) and vendoring as described above. To build packages of your beat, run the following command:

```
make package
```

This will fetch and create all images required for the build process. The hole process to finish can take several minutes.
