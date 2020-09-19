## Usage

Used to handled HttpRequest. This interface is mostly used to stub WL_HttpRequestHandler in certain scenarios, but in future evolution the Worldline Core Technical framework should have its internal logic describable through interfaces.

## Methods  

* **pass(wlHttpRequest)** 
Returns an HttpResponse, resulting from the execution or from the cache-reading of the wlHttpRequest given as an argument.