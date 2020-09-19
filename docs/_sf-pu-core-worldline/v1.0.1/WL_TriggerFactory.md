## Usage  

Factory for the injection and instantiation of trigger handlers. Typically used in ApexTriggers configured for all trigger events in order to allow for a 1 trigger per SObject logic. The injected trigger handlers must implement the [[WL_TriggerInterface]] interface. [[WL_TriggerInterface]] methods define behavior for all trigger event scenarios.

## Constructors

Factory class, cannot be constructed and is only use to build instances of other classes.

## Methods  

* **createAndExecuteHandler(type)**  
Injects an instance of the type given as an argument. The class given as type must implement the [[WL_TriggerInterface]] interface.