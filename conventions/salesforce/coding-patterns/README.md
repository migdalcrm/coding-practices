# Coding Patterns

## Transaction Control in Apex (Savepoint & Rollback)

```
public PageReference saveAccounts() {
    Savepoint sp = Database.setSavepoint();
    try {
    	// Your code logic here...
    } catch (System.Exception ex) {
        Database.rollback(sp);
        // Show error to user
    }
}
```

## SOQL
Don't use inline SOQL queries, as it mingles business logic code with querying code. Instead, we'll have a central SOQL Builder class, which all code will use (this is called "Selector Layer", see more [here](https://trailhead.salesforce.com/content/learn/modules/apex_patterns_dsl?trailmix_creator_id=abrarsheikhsony&trailmix_slug=oop-in-apex)).

## Calling Web Services
Calling web services should be done through a service agent class (this is called "Service Layer", see more [here](https://trailhead.salesforce.com/content/learn/modules/apex_patterns_sl?trailmix_creator_id=abrarsheikhsony&trailmix_slug=oop-in-apex)).

## try-catch block
TBD.

## Logging
TBD.
