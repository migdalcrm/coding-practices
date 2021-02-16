# Coding Patterns

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

### Jobs Logs

- Every job should write to a `bs_jobslog` record.
- Every job may write to a log file using `log4net`.


