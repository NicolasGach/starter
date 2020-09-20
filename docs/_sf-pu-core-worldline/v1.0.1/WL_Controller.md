---
layout: documentation
codeversion: v1.0.1
---

## Usage

Controller class used to pilot transactions with the database in the Worldline Core Technical framework.

## Constructors

Non constructible, an instance of the class is returned by the *getInstance()* method, this instance is generated once via static initialization.

## Methods

* **register(wlSObjectRecord)**   
Register an instance of the [[WL_SObjectRecord]] class with the controller.  

* **buildCommit()**  
Prepares the commit of transactions to the database by digestion the [[WL_SObjectOrder]] made on the registered [[WL_SObjectRecord]] objects. "PULL" and "PULL" orders are merged in an "at most" logic, i.e. the merge stops when the state of an [[WL_SObjectRecord]] is considered to be changing as a consequence of an order in the pile of [[WL_SObjectOrder]].  

* **execute()**  
Executes the transactions built via the *buildCommit()* method. Will also call the callback methods registered [[WL_SObjectRecord]] records once a transaction is complete.

* **deliver()**  
Shorthand for a call to *buildCommit()* followed by a call to *execute()*.  

* **flush()**  
Clears the pile of [[WL_SObject]] after a call to *execute()*.