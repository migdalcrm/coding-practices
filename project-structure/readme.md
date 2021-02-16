# Project Structure

The following are non-mandatory recommendatios.

## Folder Structure

Plugins dlls, custom actions dlls, job apps and javascript scripts should be placed in folders named by business entities.

### Examples

#### Plugins

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

#### Actions

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

#### Javascript and HTML

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

## Code Reuse Between Dlls

Duplicating code should be avoided. 
If some code needs to be reused between different dlls, Shared Projects or Linked Files should be used.

### Examples

-	CRM proxy classes (late bound generated code).
-	Custom Action's request and response (e.g., when the custom action is called from both plugin and job).
