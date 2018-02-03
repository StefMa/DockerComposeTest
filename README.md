# DockerComposeTesting
Just a simple example how Dockers compose works.

## Project
The project contains a "Gradle project" which have a task called `BuildCopy` which just copy it's `build.gradle` to the Dockers `/test` directory.

This `/test` dir is mapped to the hosts `outputVolume` which is accessible for other services as well.

The second service (`printService`) will just look into the shared `outputVolume` and then print the content of the `build.gradle`.

## Run
Run it with
```
docker-compose up
```
It will generate the `outputVolume` which will then contain the `build.gradle` file.
