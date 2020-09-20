---
layout: documentation
codeversion: v1.0.1
---

## Usage

Wrapper for an SObject definition, used to cache SObject definition information and to perform a couple additional operations.

## Constructors  

This class can only be instantiated by calling the *getObject(sObjectType)* method, which will also manage the caching of object definitions.

## Methods  

* **getObject(sObjectType)**  
Creates an instance of WL_SObject wrapping the sObjectType provided as argument. If such an instance already exists, return it instead. Returns an WL_SObject instance.  

* **getType()**  
Returns the wrapped object SObjectType.  

* **getTypeName()**  
Returns the wrapped object SObjectType name as a String.  

* **getObjectDescribe()**  
Returns the wrapped object DescribeSObjectResult.  

* **getObjectFields()**  
Returns the field map for the wrapped object.  

* **getFieldDescribes()**  
Returns the DescribeFieldResult map for the wrapped object.  

* **getFieldNames()**  
Returns the list of field names for the wrapped object.