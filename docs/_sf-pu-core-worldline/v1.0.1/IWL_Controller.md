## Usage

Interface for the controller in the Worldline Core Technical framework. Classes implementing it satisfy the requirements to be used as WCT controllers.  

## Methods

* **deliver()**  
This method should combine the building of database commits and their execution. It ought as well to trigger callbacks related to said execution in the object subscribed to the controller, by indicating the "done" status of orders when their handling is done.

* **register(wlSObjectRecord)**  
Registers a subscriber to the controller. Subscribing SObject wrappers have their database transaction orders handled by the controller. 