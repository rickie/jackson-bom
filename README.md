# jackson-bom

A "bill of materials" POM for Jackson dependencies.

Since Jackson 2.9.2 also contains `jackson-base` internal parent for actual Jackson
components: this should not be relied by components other than standard Jackson
component maintained by development team. It is bundled here for convenience.

## Status

[![Build Status](https://travis-ci.org/FasterXML/jackson-bom.svg)](https://travis-ci.org/FasterXML/jackson-bom)
[![Tidelift](https://tidelift.com/badges/package/maven/com.fasterxml.jackson:jackson-bom)](https://tidelift.com/subscription/pkg/maven-com-fasterxml-jackson-jackson-bom?utm_source=maven-com-fasterxml-jackson-jackson-bom&utm_medium=referral&utm_campaign=readme)

## Usage

There are two ways to use the BOM pom: either as parent pom:

```xml
  <parent>
    <groupId>com.fasterxml.jackson</groupId>
    <artifactId>jackson-bom</artifactId>
    <version>2.13.1</version>
  </parent>
```

or by importing just the dependencies:

```xml
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>com.fasterxml.jackson</groupId>
            <artifactId>jackson-bom</artifactId>
            <version>2.13.1</version>
            <scope>import</scope>
            <type>pom</type>
        </dependency>   
    </dependencies>
</dependencyManagement>
```

Two approaches are same with respect to dependency inclusion; latter ONLY includes dependencies,
former includes many other settings.
Usually latter is preferable, unless component is very closely coupled with core Jackson components.

## Secondary

Note that this repo ALSO contains `jackson-base` (see under dir `base/`), which is the intended
parent pom for Jackson core components. It extends `jackson-bom`, augmenting with settings that
are only/mostly relevant for Jackson components, but not to things that depend on Jackson in general.
Use of `jackson-base` is not recommended for libraries that are not meant to be coupled with Jackson
release cycle and settings.

## Support

### Community support

Jackson components are supported by the Jackson community through mailing lists, Gitter forum,
Github issues. See [Participation, Contributing](../../../jackson#participation-contributing)
for full details.

### Enterprise support

Available as part of the Tidelift Subscription.

The maintainers of `jackson-bom` and thousands of other packages are working with Tidelift to deliver
commercial support and maintenance for the open source dependencies you use to build your applications.
Save time, reduce risk, and improve code health, while paying the maintainers of the exact dependencies
you use.
[Learn more.](https://tidelift.com/subscription/pkg/maven-com-fasterxml-jackson-jackson-bom?utm_source=maven-com-fasterxml-jackson-jackson-bom&utm_medium=referral&utm_campaign=enterprise&utm_term=repo)
