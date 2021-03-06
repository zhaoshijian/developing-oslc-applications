The [OSLC Core specification](https://archive.open-services.net/bin/view/Main/OslcCoreSpecification) defines the basic patterns and protocols that any OSLC software must implement. The other workgroups define additional resources or extend existing ones, but they do not add new protocols.

Here are the major resources defined in the [OSLC Core specification](https://archive.open-services.net/bin/view/Main/OslcCoreSpecification):

| Resource or Pattern | Description | More information |
| ------------------- | ----------- | ---------------- |
| Service Provider | A resource that describes a collection of resources and tells you how to create new resources, find existing resources, or expose a user interface to do either | [OSLC Primer: Service Provider](https://open-services.net/resources/oslc-primer/#serviceprovider) |
| Resource Paging | A pattern to break long lists of resources into smaller pages, and provide a URL for the next page | [OSLC Primer: Resource Paging](https://open-services.net/resources/oslc-primer/#resource-paging) |
| Queries | Standard query string patterns to retrieve a subset of resources or properties | [OSLC Primer: Query mechanisms](https://open-services.net/resources/oslc-primer/#query-mechanisms) |
| Resource Shapes | Documents that define and describe the properties a resources should have, including acceptable values, cardinality, and whether or not those properties are required | [OSLC Primer: Resource Shapes](https://open-services.net/resources/oslc-primer/#resourceshapes) |
| Creation Factory | A service that creates new resources and (via HTTP `POST`) and may also provide the Resource Shape for new resources | [Core 2.0: Creation Factories](https://archive.open-services.net/bin/view/Main/OslcCoreSpecification#Creation_Factories)
| Service Provider Catalog | A resources that lists a set of ServiceProviders | [OSLC Primer:  ServiceProvider](https://open-services.net/resources/oslc-primer/#serviceprovider) |
| Delegated User Interface (UI) dialogs | A method for embedding an interface to create or find resources inside another tool | [OSLC Primer: Delegated UI dialogs](https://open-services.net/resources/oslc-primer/#delegated-user-interface-dialogs) |
| UI Previews | A method for discovering and displaying a preview of a resource in another tool | [OSLC Primer: UI Preview](https://open-services.net/resources/oslc-primer/#ui-preview) |


To explore some of our other specifications, the OSLC Core Workgroup maintains [a list of OSLC vocabularies and specifications](https://archive.open-services.net/wiki/core/Vocabulary-index/) that includes relationship diagrams.
