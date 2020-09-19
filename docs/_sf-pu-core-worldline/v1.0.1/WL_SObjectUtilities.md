## Usage

Utility methods for manipulating SObject instances

## Constructor

Utility class, not instantiable, all methods are static.

## Methods

* **push(sobjects)**  
Update DML operation for the provided sobjects.  

* **pull(ids, fields)**  
Shorthand for *pull(ids, objectDescribe, fields)*. Returns the query result.

* **pull(ids, objectDescribe, fields)**  
Select database operation performed on the records which Ids are provided in the ids argument, and which scope is provided in the fields argument. Will append RecordType fields if omitted from fields. Returns the query result.

* **flattenMap(fieldMap)**  
Shorthand for *flattenMap(fieldMap, depth)*, where depth is initialized at 1. Returns a flat list of fields in SOQL notation.

* **flattenMap(fieldMap, depth)**
Returns a flat list in SOQL notation generated from the fieldMap argument. The fieldMap argument would typically be obtained by calling getPopulatedFields on an SObject instance. As it is a recursive method, the depth argument controls the depth of recursion, stopping at 5.  

* **mergeStates(sObjectOrder, sObject)**  
Shorthand for *mergeStates(sObject, sObject, fieldDescribes)*. The first sObject argument and the fieldDescribes is retrieved from the underlying sObject of the [[WL_SObjectOrder]] instance provided as first argument. Returns the SObject resulting from the merge.

* **mergeStates(sObject, sObject, fieldDescribes)**  
Returns an sObject which contains the merging of fields of the first and second argument, excluding AutoNumber and Calculated fields. Returns the SObject resulting from the merge.