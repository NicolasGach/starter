---
layout: documentation
codeversion: v1.0.1
---

## Usage

A wrapper for a database command, attached to a [[WL_SObjectRecord]]. Implements Comparable interface to allow for the sorting of List\<WL_SObjectOrder\>.

There are 5 types of supported commands :  
* PUSH : push the [[WL_SObjectRecord]] current state to the database.
* PULL : pull the full state of the [[WL_SObjectRecord]] from the database.
* PULLSOME : pulls a specific target state from the database for the [[WL_SObjectRecord]] in scope.
* PULLMORE : pulls other fields on top of the current state of the [[WL_SObjectRecord]] from the database.
* REFRESH : **Deprecated** pulls the current state of the [[WL_SObjectRecord]] from the database. To be replaced by an evolution of the PULL command.

These 5 types are part of the **Command** enum of the WL_SObjectOrder class.

## Constructors  

* **WL_SObjectOrder(wlSObjectRecord, sObject, command)**  
Creates a new instance of WL_SObjectOrder for the wlSObjectRecord argument. The target state of the command is given by the sObject argument, and the type of command by the command argument.  

* **WL_SObjectOrder(wlSObjectRecord, sObject, command, fields)**  
Similar to *WL_SObjectOrder(wlSObjectRecord, sObject, command)*, the fields argument serving to override the target state in case of a PULL type command.  

* **WL_SObjectOrder(wlSObjectOrder)**  
Creates a new instance of WL_SObjectOrder by cloning an existing one.  

## Methods  

* **getSource()**  
Returns the [[WL_SObjectRecord]] pertaining to the WL_SObjectOrder.  

* **getState()**  
Returns an SObject representing the targeted state for the WL_SObjectOrder. This SObject is a snapshot of the SObject being wrapped by the [[WL_SObjectRecord]].  

* **setState(sObject)**  
Sets the targeted state for the WL_SObjectOrder. sObject must be of the same type than the SObject record wrapped by the [[WL_SObjectRecord]]. Usually, sObject is a snapshot of this wrapped SObject record.  

* **getCommand()**  
Returns the *WL_SObjectOrder.Command* for this WL_SObjectOrder.  

* **getResult()**  
Returns an SObject representing the result of the order execution, i.e. the new state of the [[WL_SObjectRecord]] after the order execution.  

* **getId()**  
Returns an Integer, the internal Id of the WL_SObjectOrder generated upon construction.  

* **getFields()**  
Returns the Set\<String\> listing the fields part of the target state for this WL_SObjectOrder.  

* **execute()**  
Commits the WL_SObjectOrder and returns the [[WL_SObjectRecord]] updated with the result of the WL_SObjectOrder execution.

* **done()**  
Triggers the [[WL_SObjectRecord]] callback function associated to a WL_SObjectOrder execution being done.  

* **done(sObject)**  
Similar to *done()* but assign the sObject argument to the WL_SObjectOrder result.  

* **compareTo(objectToCompareTo)**  
Required implementation by the Comparable interface, defines the list sorting behavior.