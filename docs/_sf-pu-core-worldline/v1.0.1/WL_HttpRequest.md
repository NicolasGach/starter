## Usage

Wrapper for HttpRequest. Requests can be cached, in which case the result of the previous call will be returned when the endpoint is called again, without the request being passed as a callout. WL_HttpRequest can be handled as Sets.

## Constructors

* **WL_HttpRequest()**  
Creates a new instance of WL_HttpRequest.  

* **WL_HttpRequest(wlHttpRequest)**  
Creates a new instance of WL_HttpRequest by cloning an existing one.  

## Methods

* **getEndpoint()**  
Returns the request endpoint as a String.  

* **setEndpoint(endpoint)**  
Set the endpoint, returns this.  

* **getMethod()**  
Returns the request method as a String.  

* **setMethod(method)**  
Set the request method, returns this.  

* **getBody()**  
Returns the request Body as an Object. Used in combination with *getBodyType()* to cast the request body to one of the three expected types: String, Map\<String, String\>, Blob.  

* **setBody(object)**  
Sets the request body to the object value. Returns this.  

* **getBodyAsString()**  
Returns the stringified version of the Body. If the body type is Map\<String, String\>, returns an x-www-form-urlencoded request body.  

* **isCached()**  
Returns a boolean value, true if the request is currently cached. By default, requests are not cached.  

* **setCached(boolean)**  
Activates or deactives the cache for a request. Returns this. By default, requests are not cached.  

* **clearCache()**  
Clears the previously cached value for the request response. If the cache is still active on the request, a new value will be cached on the next call. Returns this.

* **equalsLoose(object)**  
Checks if two WL_HttpRequest are loosely equals, i.e. same endpoint, params, headers and body type. Returns a boolean.  

* **equals(object)**  
Overrides the standard equals method. Checks for true equality between two WL_HttpRequests by calling *equalsLoose(object)* and checking their bodies.  

* **hashCode()**  
Returns an integer. Necessary implementation to handle WL_HttpRequest as Sets.