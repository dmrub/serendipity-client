# serendipity-client
A simple client for serendipity.

## Installation & Running
Simply add serendipity-client as a dependency in your project's `pom.xml` as follows

```
<dependency>
	<groupId>de.dfki.resc28</groupId>
	<artifactId>serendipity-client</artifactId>
	<version>0.1</version>
</dependency>
```

Next, configure your `pom.xml` properties to contain **your** `serendipityURI` 
```
<properties>
    <serendipityURI>http://serendipity/affordances</serendipityURI>
</properties>
```

What is left to do, is to do is to annotate the HTTP methods of your resources that should contain affordances
```
@GenerateAffordances
@GET
@Path("/myResource")
@Produces("text/turtle")
public Response doGetAsTurtle() 
{
	...
}
``` 

## Usage
TBD.

## Contributing
Contributions are very welcome.


## License
Serendipity-client is subject to the license terms in the LICENSE file found in the top-level directory of this distribution.
You may not use this file except in compliance with the License.


## Third-party Contents
This source distribution includes the third-party items with respective licenses as listed in the THIRD-PARTY file found in the top-level directory of this distribution.


## Acknowledgements
This work has been supported by the [German Ministry for Education and Research (BMBF)](http://www.bmbf.de/en/index.html) (FZK 01IMI3001A) as part of the [ARVIDA](http://www.arvida.de/) project.