# SOAP-Based SDMX Web Services: WSDL Operations and Behaviours

## Introduction

This section addresses the operations and behaviours specific to SOAP-based Web Services. Most important is a list of standard WSDL operations, which will form the basis of, and be accompanied by, actual standard WSDL XML instances, for use in development packages. There are also several guidelines for the implementation of web services, to support interoperability. 

All SDMX SOAP web services should be described using WSDL instances. The global element for each XML data and metadata format within SDMX should be specified as the content of the replies to each exchange. The function names for each identified pattern are specified below, along with the type of SDMX-ML payload. 

Because SOAP RPC is not supported, the “parameters” of each function are simply an instance of the appropriate SDMX-ML message type. As noted above, `<wsdl:import>` should be used to specify the schema for a multiple-message exchange. The distributed WSDL files illustrate how SOAP messages should be used. 

The bindings included in the distributed WSDL files are according to SOAP 1.1.