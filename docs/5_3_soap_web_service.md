## SOAP Web Service

SOAP web services should indicate errors using the standard SOAP error mechanism, using the specific namespace created for this purpose. In addition, whenever appropriate(<sup>[24](#fn-24)</sup>), the error should also be returned using the error message offered starting with version 2.1 of SDMX-ML.

In case of error, the following elements should be set in the SOAP Envelope:

- the <faultcode> element for the error number
- the <faultstring> element for the description
- the <faultactor> element for the webservice method with the url for the webservice prefixed
- The <detail> element is optional, and can be used by the service provider to provide any additional information deemed useful

According to SOAP 1.1 recommendations, the <faultcode> may be any of the following values: Server, Client, VersionMismatch, MustUnderstand under namespace "http://schemas.xmlsoap.org/soap/envelope/", extend the above codes using the character "." (dot), e.g. Server.Authentication, or use any QName for custom codes.
In the context of the SDMX Fault Code specification:
- All client-caused errors should extend the faultcode 'Client' using the character "." (dot) and followed by the appropriate code defined in section 5.5, e.g. Client.100;
- All server-caused errors should extend the faultcode 'Server' using the character "." (dot) and followed by the appropriate code defined in section 5.6, e.g. Server.500;
- All custom errors should use the faultcode 'Custom' extended using the character "." (dot) and followed by the appropriate code defined in section 5.7, e.g. Custom.1000.

<a name="fn-24"></a>[24] According to the SOAP version Framework 1.2, it is not possible to place both a <faultcode> element and return other information.
