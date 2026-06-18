# Ad Service

The Ad service provides advertisement based on context keys. If no context keys are provided then it returns random ads.

## Building locally

The Ad service uses gradlew to compile/install/distribute. Gradle wrapper is already part of the source code. To build Ad Service, run:

```
./gradlew installDist
```
It will create executable script src/adservice/build/install/hipstershop/bin/AdService

### Upgrading gradle version
If you need to upgrade the version of gradle then run

```
./gradlew wrapper --gradle-version <new-version>
```

## Building docker image

From `src/adservice/`, run:

```
docker build ./
```


## Protos (shared dependency)

This service uses the shared gRPC definitions from the separate `protos` repository.
Check it out as a sibling directory so it is available at `../protos`:

```
parent/
├── protos/      # shared protos repo (demo.proto, grpc/health)
└── <this repo>/ # this service
```

Pre-generated gRPC stubs are already committed here, so the `protos` repo is only
needed when regenerating them via `./genproto.sh`.
