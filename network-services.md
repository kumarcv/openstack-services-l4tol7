**API list**
============

**Network Service**

*List Network Services *

<table>
	<tr>
		<th>Verb</th><th>URI</th><th>Description</th>
	</tr>
	<tr>
		<td>GET</td><td>/networkservices</td><td>List all network services</td>
	</tr>
</table>

Normal Response Code(s): 200, 203
Error Response Codes(s): computeFault (400, 500, …), serviceUnavailable (503), unauthorized (401), forbidden (403), badRequest (400), badMethod (405), overLimit (413)

Example JSON response

```
	{
		"network-services":[
			{
				"id": "52415800-8b69-11e0-9b19-734f6af67565",
				"category": "firewall",
				"description": "Firewall Security appliance"
			},
			{
				"id": "493454534-8b69-11e0-9b19-74f6af672345",
				"category": "IPS",
				"description": "Intrusion Prevention Appliance"
				
			}
		]
	}
```

*create a Network service*

<table>
	<tr>
		<th>Verb</th><th>URI</th><th>Description</th>
	</tr>
	<tr>
		<td>POST</td><td>/networkservices</td><td>Create a network service</td>
	</tr>
</table>

Normal Response Code(s): 202

Error Response Code(s): computeFault (400, 500, …), serviceUnavailable (503), unauthorized (401), forbidden (403), badRequest (400), badMethod (405), overLimit (413), itemNotFound (404), badMediaType (415), serverCapacityUnavailable (503)

This operation creates a network service category. Each category is identified by UUID.

The following table describes the required and optional attributes that you can specify in the request body.

<table>
	<tr>
		<th>Name</th><th>Description</th><th>Required</th>
	</tr>
	<tr>
		<td>category</td><td>/Type of network service grouped as category. Following are few categories firewall, IPS, WAF etc., User can create category of his choice </td><td>Yes</td>
		<td>description</td><td>Describe about the category</td><td>False</td>
	</tr>
</table>

*Network service create JSON request*

```
	{
		"category": "firewall",
		"description": "Firewall Security appliance"
	}
```

*Network service create JSON response*

```
	{
		"id": "52415800-8b69-11e0-9b19-734f565bc83b",
		"tenant-id": "35415810-6b62-71e0-0b11-234f565bc422",
		"category": "firewall",
		"description": "Firewall Security appliance"
	}
```

*Get Network Service Details*
