The [Eclipse Lyo](http://www.eclipse.org/lyo/) project supports Java developers with the development of REST-based servers and clients that need to share heterogeneous information as [RDF resources](https://www.w3.org/TR/rdf11-primer/).

Eclipse Lyo promotes the use of Linked Data principles and the [OSLC](http://docs.oasis-open.org/oslc-core/oslc-core/v3.0/oslc-core-v3.0-part1-overview.html) (Open Services for Lifecycle Collaboration) standard for publishing lifecycle data, to enable the interoperability of heterogeneous products, services, and other distributed network resources.

Below are the main active components of the Eclipse Lyo projects. 

See [Sample applications and code](/sample-applications-and-code.html) for example applications that are based on Eclipse Lyo.  

# <a name="oslc4j-sdk"></a>OSLC4J SDK

Lyo’s central component is the OSLC4J SDK (Software Development Kit) that helps build REST-based servers and clients, compliant with the OSLC standard.

The library:

* Allows an OSLC server to publish their RESTful API capabilities, based on the [OSLC Discovery](http://docs.oasis-open.org/oslc-core/oslc-core/v3.0/oslc-core-v3.0-part2-discovery.html) approach. This in turn facilitates for clients to discover and use available capabilities.
* Provides an OSLC server with JAX-RS Providers and utility classes to facilitate the development of REST operations for accessing, creating, updating and deleting RDF resources.
* Provides an OSLC Client with helpful APIs to interact with OSLC Servers. It provides an additional layer of functionality on top of Apache HttpClient, Apache Wink, and OSLC4J that can give you a head start on some of the common use cases such as form login, OAuth handling, service discovery, sending queries, and processing query results.
* Automates the marshaling/unmarshaling of Java objects to/from Linked Data RDF resources ([Apache Jena](https://jena.apache.org/) model).

**You do not have to use the Eclipse application to use the OSLC4J SDK**: Although much of the documentation assumes you will be using Eclipse, the SDK is available as maven libraries, as detailed [Setup an OSLC Provider/Consumer Application](./setup-an-oslc-provider-consumer-application).</div>


**Further Information**

* Explore our [tutorials to use the OSLC4J SDK when building an OSLC Server and/or client application](../tutorials).
* How to [setup an OSLC Server and/or Client](./setup-an-oslc-provider-consumer-application).
* Javadocs for 
   * [oslc4j-core , Lyo release 4.0.0](https://download.eclipse.org/lyo/docs/core/4.0.0-SNAPSHOT/) - support for JAX-RS 2.0, with no dependency on any particlar implementation of JAX-RS.
   * [oslc4j-core , Lyo release 2.4.0 and earlier](https://download.eclipse.org/lyo/docs/core/2.4.0/) - legacy support for JAX-RS 1.0, and the Apache Wink implementation.
   * [oslc4j-client, Lyo release 4.0.0](https://download.eclipse.org/lyo/docs/oslc4j-client/latest) - support for JAX-RS 2.0, with no dependency on any particlar implementation of JAX-RS.
   * [oslc-java-client, Lyo release 2.4.0 and earlier](https://download.eclipse.org/lyo/docs/oslc-java-client/latest) - legacy support for JAX-RS 1.0, and the Apache Wink implementation. 
* [Lyo Client sample code](https://github.com/OSLC/lyo-samples) - A Github repository that includes sample code to demonstrates how to use the Lyo OSLC4J SDK oslc4j-client to interact with OSLC Service Providers in various ways. It addresses a variety of common OSLC use cases including login, OAuth, service discovery, and queries. See the [README.md](https://github.com/OSLC/lyo-samples/blob/master/README.md) file in the repository for further pointers.
* You are also welcome to contact the development team via [lyo-dev mailing list](https://dev.eclipse.org/mailman/listinfo/lyo-dev)

# <a name="lyo-designer"></a>Lyo Designer

[Lyo Designer](lyo-designer) is an Eclipse plugin that allows one to graphically model (1) the overall system architecture, (2) the information model of the RDF resources being shared, and (3) the individual services and operations of each Server in the system. The figure below shows the information modelling interface:

![An example domain specification diagram](images/LyoToolchainModel-SpecificationDiagram.png)

Lyo Designer includes a integrated code generator that synthesizes the model into almost-complete OSLC4J-compliant running implementation.
The resulting code includes:

* Java classes with appropriate OSLC4J-annotations to reflect the modelled RDF resource shapes
    * This automates the marshaling/unmarshaling of Java instances as Linked Data RDF resources.
* JAX-RS Service operations for accessing, updating, creating and deleting RDF resources.
    * These operations handle any of the supported formats (turtle, RDF/XML, Json, etc.)
    * For debugging purposes, JSP pages are also produced to deliver HTML representations of all RDF resources.
* JAX-RS Service operations to completely handle [Delegated UI](http://docs.oasis-open.org/oslc-core/oslc-core/v3.0/cs01/part4-delegated-dialogs/oslc-core-v3.0-cs01-part4-delegated-dialogs.html) for both creation and selection dialogs.
    * Including the initial generation of basic JSP pages for the html-representation of the dialogs.
* JAX-RS Service operations to handle [Resource Preview](http://docs.oasis-open.org/oslc-core/oslc-core/v3.0/cs01/part3-resource-preview/oslc-core-v3.0-cs01-part3-resource-preview.html)
    * Including the initial generation of basic JSP pages for the html-representation of the resource previews.

Lyo Designer supports incremental development, where manual changes to the generated code are preserved upon changes to the model, and subsequent code regeneration.

**Further Information**

* How to [install Lyo Designer](./install-lyo-designer)
* How to use Lyo Designer to [model a toolchain](./toolchain-modelling-workshop) and generate an initial code base
* How to use Lyo Designer to [model domain specifications](./domain-specification-modelling-workshop), and generate OSLC4J-annotated Java classes to reflect the defined OSLC Resources.
* If you want to contribute to Lyo Designer, you can [work from its source code](https://github.com/eclipse/lyo.designer/wiki/Working-from-Source-Code)


# <a name="trs-sdk"></a>OSLC Tracked Resource Set (TRS) SDK

[OSLC Tracked Resource Set (TRS) SDK](https://wiki.eclipse.org/Lyo/TRSSDK) provides a set of java beans that represent the entities within the [TRS specification 2.0](https://archive.open-services.net/wiki/core/TrackedResourceSet-2.0/). (this specification is being migrated to OASIS, as [TRS 3.0 specification](https://raw.githack.com/oasis-tcs/oslc-core/master/specs/trs/tracked-resource-set.html).)

**Further Information**

* [Javadocs for TRS package](https://download.eclipse.org/lyo/docs/core/latest/index.html?org/eclipse/lyo/core/trs/package-summary.html)
* [Guide on implementing a TRS provider for the iotp-adaptor](../iotp_adaptor/trs-provider) and integrating with the IBM jazz.net applications. The iotp-adaptor an OSLC server that exposes IBM Watson IoT Platform resources as OSLC resources.
* [In-memory TRS Server](./setup-an-oslc-provider-consumer-application.html#provide-trs-support) - Instructions on how to integrate a simple TRS Server implementation that does not persist its TRS resources.
   * [TRS Server Javadocs](https://download.eclipse.org/lyo/docs/trs-server/latest/)
* [TRS Reference Application guided tour](https://wiki.eclipse.org/Lyo/TRSReferenceApplication) - Provides a guided tour of the TRS reference application and its capabilities.
* [TRS Workshop](http://wiki.eclipse.org/Lyo/TRSWorkshop) - A TRS workshop for Bugzilla

# <a name="additional-components"></a>Additional components

Additional components of the Lyo project include:

* [Lyo Store](https://github.com/eclipse/lyo-store) - a library that provides a simple interface for working with a triplestore via Java objects representing OSLC Resources.
* [Test Suite](https://wiki.eclipse.org/Lyo/LyoTestSuite) - provides a suite of tests which will test OSLC domain provider implementations against the specification.
* [Reference Implementations](https://wiki.eclipse.org/Lyo/BuildingOSLC4J) - See how OSLC works directly with working samples and with a simple server to test against.
* [_Reference Implementations (OUTDATED)_](https://github.com/eclipse/lyo.rio) - a simple, bare-bones reference implementation of the OSLC specifications. RIOs are intended to help those who are adopting OSLC by providing a functioning system that can be explored via a simple UI and REST services, or by taking a look at the source code.
* [**Perl libraries and samples**](http://wiki.eclipse.org/Lyo/LyoPerl): modules for Perl for interacting with OSLC providers, including the [Net-OSLC PERL library](http://arroway.github.com/Net-OSLC-CM/)
* [_OSLC4JS Javascript OSLC library (experimental)_](https://wiki.eclipse.org/Lyo/Oslc4Js).
    - [OSLC4JS architecture](http://oslc.github.io/developing-oslc-applications/oslc-open-source-node-projects.html)
    - [Development with OSLC4JS](https://wiki.eclipse.org/DevelopingOslc4Js)

