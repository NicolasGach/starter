---
layout: default
codeversion: v1.0.1
---
# Core Worldline Package

## Short summary

### [[WL_SObjectRecord]]

Abstract wrapper for any SObject, allowing to harmonize the data pushing / pulling to and from the database.

Handles the definition of units of work for SObjects and the virtualization of database operations.

### [WL_SObjectUtilities](#WL_SObjectUtilitiesA)

Utility methods for interacting with the database, can be used as a stand alone tool but mostly used by the SObject Wrapper to handle operations such as *refresh*, *pull* and *push*.

### [WL_Injector](#WL_InjectorA)

Dependency injection, allowing for a simpler management of dependencies and easier stubbing in test classes.

### [WL_TriggerFactory](#WL_TriggerFactoryA) & [WL_TriggerInterface](#WL_TriggerInterfaceA)

Streamlining of trigger definition, using injection of handler in trigger in order to perform trigger-based operations. The goal is 1 trigger for 1 sobject.

### [WL_HttpRequestHandler](#WL_HttpRequestHandlerA)

Handler for Http callouts, paired with a custom wrapper around http requests. Allows for caching and historization of requests, as well as a cleaner management of request related information (headers, body, query ...)

### Mock Objects

Two mock objects are provided solely for test purposes, in order to be able to test abstract logics outside of configuration items which will be handled by other packages using this one as a dependency.