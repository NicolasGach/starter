---
layout: documentation
codeversion: v1.0.1
---

## Usage

Handler for [[WL_HttpRequest]] objects. Is called internally by other classes to pass the requests.

## Constructors  
* **WL_HttpRequestHandler()**  
Creates a new WL_HttpRequestHandler instance.  

## Methods

* **isCached(wlHttpRequest)**  
Checks if the [[WL_HttpRequest]] argument is cached. Returns a boolean.  

* **(Beta) getHistory()**  
Returns a List\<[[WL_HttpRequest]]\>, which are the previously handled request by the WL_HttpRequestHandler.  

* **pass(wlHttpRequest)**  
Performs the request defined by the [[WL_HttpRequest]] given as an argument. Returns the request's response.