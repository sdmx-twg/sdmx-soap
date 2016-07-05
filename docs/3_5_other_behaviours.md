## Other Behaviours

### Versioning Defaults

When no version is specified in the message invoking a service, the default is to return the last production version of the resource(s) requested.

### Resolving References and Specifying Returned Objects

Version 2.1 of the SDMX-ML Query message offers new functionality to resolve reference and specify the type of objects to be returned. The SOAP API relies on this mechanism for resolving references and specifying returned objects. See Section “[https://github.com/sdmx-twg/sdmx-rest/blob/master/v2_1/ws/rest/docs/4_3_structural_queries.md#applicability-and-meaning-of-references-attribute](Applicability and meaning of references attribute)”.

### Enabling compression

Compression should be enabled using the appropriate HTTP Header field (Accept-Encoding).

### Implementation of the SOAP based SDMX Web Services

In the SDMX Web Services, the development is Contract-First since the WSDL has been specified by the standard. Furthermore it is a Web Service of already prepared XML messages requests/responses, i.e. the interfaces for the application logic are the XML messages. Therefore there is no need to generate stubs for serialisation and de-serialisation of the SOAP payloads from/to the native language classes. The indicative way is to have full control on the XML messages requests/responses. When using the automatic generation of code it will include an extra element for the parameter of the operation in the SOAP request according to the RPC paradigm, and to the SOAP specifications that is not desired according to the standardised SDMX WSDL.

When using Apache Axis in Java, an interface for the service is offered by the toolkit that reads/returns the XML payloads using DOM elements (`DOMElement` in Axis2). Moreover when using the Java API for XML Web Services (JAX-WS), the developer can use the `Provider<SOAPMessage>` interface, where he is responsible for creating the SOAP request and response messages as well as specifying the standardised WSDL of the service.

However in the .NET environment there is no similar solution for this. The developer of the service will have to use the `XmlAnyElement` parameter for the .NET web methods. This specifies that the parameter of the Service method can be any XML element thus allows the developer to take control of the XML payload. The details of this approach are presented in the “Annex I: How to eliminate extra element in the .NET SDMX Web Service” in the section 06 of the SDMX documentation.

### Compliance with WS-I

To ensure interoperability between SDMX web services, compliance with sections of the WS-I Profile 1.1 is recommended for all SDMX web services. The documentation can be found at [http://www.ws-i.org/Profiles/BasicProfile-1.1-2004-08-24.html](http://www.ws-i.org/Profiles/BasicProfile-1.1-2004-08-24.html). The recommended sections are those concerning the use of SOAP and WSDL. UDDI, while useful for advertising the existence of SDMX web services, is not necessarily central to SDMX interoperability.
  