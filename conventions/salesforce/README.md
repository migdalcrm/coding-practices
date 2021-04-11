# Calling Web Services
Calling web services should be done through a service agent class (this is called "Service Layer", see more [here](https://trailhead.salesforce.com/content/learn/modules/apex_patterns_sl?trailmix_creator_id=abrarsheikhsony&trailmix_slug=oop-in-apex)).

# Naming Conventions

### Customization
<table>
	<tr>
		<th>Component</th>
		<th>Naming Convention</th>
	</tr>
	<tr>
		<td>
			Custom Object Name<br/>
			Record Types<br/>
			Custom Buttons & Links<br/>
		</td>
		<td>PascalCase without Underscores</td>
	</tr>
	<tr>
		<td>
			Custom Field Name<br/>
		</td>
		<td>camelCase without Underscores</td>
	</tr>
</table>

### Apex

<table>
	<tr>
		<th>Component</th>
		<th>Naming Convention</th>
		<th>Examples with Suffix</th>
	</tr>
	<tr>
		<td>Apex Trigger</td>
		<td>PascalCase without Underscores</td>
		<td>AccountTrigger</td>
	</tr>
	<tr>
		<td>Apex Trigger Handler Class</td>
		<td>PascalCase without Underscores</td>
		<td>AccountTriggerHandler</td>
	</tr>
	<tr>
		<td>Apex Utility Class</td>
		<td>PascalCase without Underscores</td>
		<td>AccountUtility</td>
	</tr>
	<tr>
		<td>Apex Helper Class</td>
		<td>PascalCase without Underscores</td>
		<td>AccountRollupHelper</td>
	</tr>
	<tr>
		<td>Apex Wrapper class</td>
		<td>PascalCase without Underscores</td>
		<td>AccountWrapper</td>
	</tr>
	<tr>
		<td>Apex Batch Class</td>
		<td>PascalCase without Underscores</td>
		<td>ProcessAccountsBatch</td>
	</tr>
	<tr>
		<td>Apex Schedule Class</td>
		<td>PascalCase without Underscores</td>
		<td>ProcessAccountsBatchSchedule</td>
	</tr>
	<tr>
		<td>Apex/Visualforce Controller</td>
		<td>PascalCase without Underscores</td>
		<td>AccountController</td>
	</tr>
	<tr>
		<td>Apex/Visualforce Controller Extension</td>
		<td>PascalCase without Underscores</td>
		<td>AccountControllerExtension</td>
	</tr>
	<tr>
		<td>Apex Test Data Factory</td>
		<td>PascalCase without Underscores</td>
		<td>AccountTestDataFactory</td>
	</tr>
	<tr>
		<td>Apex Test Class Name</td>
		<td>PascalCase without Underscores</td>
		<td>AccountTest</td>
	</tr>
</table>

### Lightning

<table>
	<tr>
		<th>Component</th>
		<th>Naming Convention</th>
		<th>Examples with Suffix</th>
	</tr>
	<tr>
		<td>Lightning Application</td>
		<td>PascalCase without Underscores</td>
		<td>HRMApp</td>
	</tr>
	<tr>
		<td>Lightning Interface</td>
		<td>PascalCase without Underscores</td>
		<td>PaginationInterface</td>
	</tr>
	<tr>
		<td>Lightning Component</td>
		<td>PascalCase without Underscores</td>
		<td>ProcessRecordsComponent</td>
	</tr>
	<tr>
		<td>Lightning Token</td>
		<td>lowerCamelCase without Underscores</td>
		<td>integrationCredentialsToken</td>
	</tr>
	<tr>
		<td>Lightning Application Event</td>
		<td>camelCase with Underscores</td>
		<td>deleteRecord</td>
	</tr>
	<tr>
		<td>Lightning Component Event</td>
		<td>camelCase with Underscores</td>
		<td>sendAccountToSAP</td>
	</tr>
</table>
