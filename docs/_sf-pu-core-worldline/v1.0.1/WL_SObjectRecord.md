
## Usage

This class is **abstract** therefore cannot be instantiated without being extended.

## Constructors

* **WL_SObjectRecord(ID,List\<String\>)**  
Creates a new SObjectWrapper instance for the SObjectType of the record provided as the ID value, initialized with the field apiNames provided in the List\<String\> variable.  
* **WL_SObjectRecord(SObject,List\<String\>)**  
Creates a new SObjectWrapper instance for the SObjectType of the record provided as the SObject value, initialized with the field apiNames provided in the List\<String\> variable.

* **WL_SObjectWrapper(ID)**  
Creates a new SObjectWrapper instance for the SObjectType of the record Id provided as the ID value.

* **WL_SObjectWrapper(SObject)**  
Creates a new SObjectWrapper instance for the SObjectType of the record provided as the SObject value.

## Methods

* **getSObject()**  
Returns the WL_SObject instance for the SObjectType of the wrapped record.
* **getOrder()**  
Returns the list of database transaction orders currently registered for this record.
* **getStateFields()**  
Returns the set of fields currently composing the wrapped record's state.
* **pull()**  
Registers a database order to retrieve the fields currently part of the wrapped record's state
* **pullNow()**  
Similar to *pull()*, but executes the database order upon invocation.
* **pull(fields)**  
Registers a database order to retrieve the record from the database, based on the state described in the specified fields.
* **pullMore(fields)**  
Registers a database order to retrieve the wrapper record from the database, with the fields part of its current state augmented by the specified fields.
* **pullMoreNow(fields)**  
Similar to *pullMore(fields)* but executes the database order upon invocation.
* **pullAll()**  
Registers a database order to retrieve the full database state of the record, for all depth 1 fields.
* **pullAllNow()**  
Similar to *pullAll()* but executes the database order upon invocation
* **push()**  
Registers a database order to save the wrapped record's current state to the database.
* **pushNow()**  
Similar to *push()* but executes the database order upon invocation.
* **orderDone(orderId)**  
Triggers the callback function for an order execution, which Id is specified by orderId. The callback function called by *orderDone(orderId)* shoud be overriden by child classes when extending WL_SObjectRecord.
* **digestOrders()**  
Compiles registered database orders to exclude irrelevant transactions from the pile.
* **flush()**  
Empties the database order pile after storing the database orders in the order history.
* **commitCallback(command)**  
Executes the callback for the specified database order type in the command parameter. **Protected virtual** method, to be overriden by Child classes to define their own callback behavior.