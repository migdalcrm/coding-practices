# Coding Patterns

## Project Structure

The following are non-mandatory recommendatios.

### Folder Structure

Plugins dlls, custom actions dlls, job apps and javascript scripts should be placed in folders named by business entities.

#### Examples

##### Plugins

```
.
└── Plugins.dll
    └── Email
        ├── BPL
        |    ├── EmailBpl.cs            // only contains calls to function defined in EmailBplWorkflows.cs
        |    ├── EmailBplWorkflows.cs 
        |    └── EmailBplQueris.cs      // contains only queries
        └── Stages
             ├── PostCreateEmail.cs            // only contains calls to function defined in EmailBplWorkflows.cs
             └── PostUpdateEmail.cs 
```

##### Actions

```
.
└── Actions.dll
    └── Email
        └── SendByHafazaIrgunit
            ├── SendByHafazaIrgunit.cs
            ├── BPL
            |    ├── SendByHafazaIrgunitBpl.cs            
            |    └── SendByHafazaIrgunitQueris.cs      
            └── Containers
                 ├── SendByHafazaIrgunitRequest.cs            
                 └── SendByHafazaIrgunitResponse.cs 
```

##### Javascript and HTML

```
.
└── WebResources.dll
    ├── Scripts
    |   └── Email
    |       ├── emailForm.js    
    |       └── emailRibbon.js
    └── Pages
        └── Email
            └── viewHafazaIrgunitLogs.html
```

### Code Reuse Between Dlls

Duplicating code should be avoided. 
If some code needs to be reused between different dlls, Shared Projects or Linked Files should be used.

#### Examples

-	CRM proxy classes (late bound generated code).
-	Custom Action's request and response (e.g., when the custom action is called from both plugin and job).


## try-catch block

Only a single try-catch block should be used for each "code unit". 
A "code unit" is different for each CRM functionlity (e.g, a "code unit" of a plugin is a plugin *stage*).

#### Plugins

The try-catch block should be placed inside the `Execute` method of each plugin stage.

#### Custom Actions

The try-catch block should be placed inside the `Execute` method of each CodeActivity derived class.

#### Web Services

The try-catch block should be placed inside the endpoint method.

#### Javascript

A single try-catch block should be placed inside each of the following:
- `onLoad` handler
- `onSave` handler
- `onChange` handlers

## Custom Actions Input and Output Parameteres

- Input and output parameters of custom actions should be json strings represetned as classes.
- The class used for the output parameter should derive from the following class:  

  ```csharp
  public class ResponseBase
  {
      public bool IsSuccess { get; set; }
      public string ErrorMessage { get; set; }
  }
  ```
  
## Using Service Agents To Call Web Services

When calling web services, the call should be done inside a service agent shared project.

## Logging

### WSLogs

- When calling a web service, the service agent method should log to WSLogs.
- When providing a web service, the endpoint should log to WSLogs.

### Trace Logs (mongodb)

- Only exceptions should be logged (i.e., `EventLevel.Error`) - except for debug time.
- Exceptions should be logged inside the catch block of each "code unit".
- When debugging, other error levels may be logged, but they must be removed from the commited code once debug is done.
- In exceptional cases which have high vulnerablity for busines mafunction - info debug should be approved by Master Reviewer(Ask Hananel). 
### Jobs Logs

- Every job should write to a `bs_jobslog` record.
- Every job may write to a log file using `log4net`.


