## Usage

Interface implemented by trigger handlers instantiated by the [[WL_TriggerFactory]] class.

## Methods  

* **bulkBefore()**  
This method is called prior to execution of a BEFORE trigger. Use this to cache any data required into maps prior execution of the trigger.  

* **bulkAfter()**  
This method is called prior to execution of an AFTER trigger. Use this to cache any data required into maps prior execution of the trigger.  

* **bulkInsert()**  
This method is called iteratively for each record to be inserted during a BEFORE  trigger. Never execute any SOQL/SOSL etc in this and other iterative methods.  

* **beforeUpdate()**  
This method is called iteratively for each record to be updated during a BEFORE trigger.  

* **beforeDelete()**  
This method is called iteratively for each record to be deleted during a BEFORE trigger.  

* **afterInsert()**  
This method is called iteratively for each record inserted during an AFTER trigger. Always put field validation in the 'After' methods in case another trigger has modified any values. The record is 'read only' by this point.  

* **afterUpdate()**  
This method is called iteratively for each record updated during an AFTER trigger.  

* **afterDelete()**  
This method is called iteratively for each record deleted during an AFTER trigger.  

* **afterUndelete()**  
This method is called iteratively for each record to be undeleted during an AFTER trigger.  

* **andFinally()**  
This method is called once all records have been processed by the trigger. Use this method to accomplish any final operations such as creation or updates of other records.