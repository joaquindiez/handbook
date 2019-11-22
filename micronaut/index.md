# GOALS

Create a tutorial to use **Micronaut** with different Languajes and DataBases

## Links and Resources

* Web of Micronaut [https://micronaut.io/](https://micronaut.io/)
* Guide for using [Google Authentication in Micronaut](https://guides.micronaut.io/micronaut-oauth2-oidc-google/guide/index.html )

* [Sample With Kotlin and Send Mail](https://guides.micronaut.io/micronaut-email-kotlin/guide/index.html)

* [Guide DZone Building MicroServices with Micronaut](https://dzone.com/articles/building-microservices-with-micronaut)

* [Micronaur Authentication](https://micronaut-projects.github.io/micronaut-security/latest/guide/)
* [reactive-microservices-development-with-micronaut](https://arul.dev/2019/03/31/reactive-microservices-development-with-micronaut/)
* [micronayt api gateway](https://arul.dev/2019/04/07/micronaut-api-gateway-in-action/)

## Installing micronaut

I use SDKMAN

The following command install the last version available of micronaut

	sdk install micronaut

Now you should be able to run the CLI

```
 mn
| Starting interactive mode...
| Enter a command name to run. Use TAB for completion:
mn>

```

## Create an Java app

Run 

	mn create-app micronaut001

enter un directory micronaut001 

	cd micronaut001/

run

	./gradlew run

## Deploying the Application

we can create an executable Jar file running

	./gradlew x	

The constructed JAR file can then be executed with java -jar

	java -jar build/libs/micronaut001-0.1-all.jar


## Create a Micronaut + Kotlin + MongoDB Application

	mn create-app micronaut-kotlin-mongo01 --lang kotlin --features mongo-reactive











