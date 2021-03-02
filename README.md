# Quarkus API example with RESTEasy JAX-RS

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:
```shell script
./mvnw compile quarkus:dev
```

## Try it in your console

```shell script
curl -w "\n" http://localhost:8080/hello
```

```shell script
curl -w "\n" http://localhost:8080/hello/greeting/fernandofuentesfullstack
```

## Packaging and running the application

The application can be packaged using:
```shell script
./mvnw package
```
It produces the `quarkus-run.jar` file in the `target/quarkus-app/` directory.
Be aware that it’s not an _über-jar_ as the dependencies are copied into the `target/quarkus-app/lib/` directory.

If you want to build an _über-jar_, execute the following command:
```shell script
./mvnw package -Dquarkus.package.type=uber-jar
```

The application is now runnable using `java -jar target/quarkus-app/quarkus-run.jar`.

## Creating a native executable

You can run the native executable build in a container using:

```shell script
./mvnw package -Pnative -Dquarkus.native.container-build=true
```
```shell script
docker build -f src/main/docker/Dockerfile.native -t quarkus/getting-started .
```
```shell script
docker run -i --rm -p 8080:8080 quarkus/getting-started
```
