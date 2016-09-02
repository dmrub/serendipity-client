# serendipity-client
A simple client for [Serendipity](https://github.com/rmrschub/serendipity). 
Think of [mod_rewrite](http://httpd.apache.org/docs/current/mod/mod_rewrite.html) for Linked Data systems.


## Installation & Configuration
Simply add serendipity-client as a dependency in your project's `pom.xml` as follows

```xml
<dependency>
	<groupId>de.dfki.resc28</groupId>
	<artifactId>serendipity-client</artifactId>
	<version>0.1</version>
</dependency>
```

Next, configure your `pom.xml` properties to contain **your** `serendipityURI` 
```xml
<properties>
    <serendipityURI>http://serendipity/affordances</serendipityURI>
</properties>
```

Add a `RepresentationEnricher` to your `javax.ws.rs.core.Application` and you are good to go! 
```java
@ApplicationPath("/")
public class Server extends Application
{
	...

	@Override
	public Set<Object> getSingletons() 
	{
		...
		RepresentationEnricher enricher = new RepresentationEnricher(serendipityURI);
		return new HashSet<Object>(Arrays.asList(sthElse, enricher));
	}
	
	...
}
```

## Usage
Simply annotate the HTTP methods of the resources you wish to be enriched with affordances.
```java
@GenerateAffordances
@GET
@Path("/myResource")
@Produces("text/turtle")
public Response doGetAsTurtle() 
{
	...
}
```

## Contributing
Contributions are very welcome.


## License
Serendipity-client is subject to the license terms in the LICENSE file found in the top-level directory of this distribution.
You may not use this file except in compliance with the License.


## Third-party Contents
This source distribution includes the third-party items with respective licenses as listed in the THIRD-PARTY file found in the top-level directory of this distribution.


## Acknowledgements
This work has been supported by the [German Ministry for Education and Research (BMBF)](http://www.bmbf.de/en/index.html) (FZK 01IMI3001A) as part of the [ARVIDA](http://www.arvida.de/) project.