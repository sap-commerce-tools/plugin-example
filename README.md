> **Archived on 2020-02-16**\
> I recently switched jobs away from SAP Commerce development

# Demo Project for hybris gradle plugins

This project shows some usage examples for the hybris build plugin.\
This demo projects assumes that there is a maven repo at `https://repository.company.com/hybris-release`
that contains the specified platform artifacts

*If you can't use maven, check the [supportportal-example](https://github.com/sap-commerce-tools/supportportal-example).*

The commented build `build.gradle` hopefully explains how to use the plugins

For details about the used plugins check the [commerce-gradle-plugin wiki](https://github.com/sap-commerce-tools/commerce-gradle-plugin/wiki)

## Setup local environment

1. clone the repository
1. `./gradlew setupDev`
1. Done!

*Note:* use `gradlew` to execute the task to ensure the correct gradle version

*Disclaimer:* the final package will NOT pass the ypackagevalidator, because
the datahub war file is just a dummy file.
If you want a valid package, set `hcs.datahub = false`

## Interesting things

- the `hcs-configuration` folder does not contain folders for every environment,
  but the final package still does. This is because the `common` folder is the
  base for every environment config
- also check out how the various `*.properties` files are merged 
  (check the results in `temp/gradle-build-demo_v1.0.0-SNAPSHOT`)
- the datahub war file has the valid file name in the package
