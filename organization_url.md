# Update Organization Url
Enables an authenticated organization owner to update the organization's url.

AUTHORIZATIONS: `cookieAuth` or `bearerAuth`

## End-Point 
<details>
<summary>  PATCH  /organizations/{organization_id}/url}
 </summary>
Zuri Chat Core API

https://api.zuri.chat/organizations/{organization_id}/url

</details>

| PATH PARAMETERS |  |
| ----------- | ----------- |
| organization_id required | string |
| | Example: 6137d69b21d3c78fc9a84bdf|
|  |  |

| **REQUEST BODY SCHEMA:**  application/json |  |
| -------- | -------- |
| The structure for the entire request object |

## REQUEST SAMPLE
How requests are made.

**content type** <br> application/json

```
{ 

"url": "https://hngworkspace.zuri.chat"

}
```

## Response
Its requires an interger code and string messsage.

 ### **200** Successfully updated the resource <br>

```
RESPONSE SCHEMA: application/json

code required      integer <int32> 
message required   string 

```

## Example <br>

**content type** <br> application/json

```
{ 

"code": 200,
"message": "resource updated successfully"

}
```
For 4xx and 5xx the interger code error and string message with be displayed.

# Get an organization by its URL
Returns the organization with the given full URL. The URL does not have to be truncated to the root, it can be to any resource on the URL.


**AUTHORIZATIONS**: `cookieAuth` or `bearerAuth`
## End-Point 
<details>
<summary>  GET /organizations/url/{workspace_url}
 </summary>
Zuri Chat Core API

https://api.zuri.chat/organizations/url/{workspace_url}

</details>

Response
### **200** means the resource have been successfully retrieved <br>

```
RESPONSE SCHEMA: application/json

code required      integer <int32> 
message required   string 
data required      object(organization)

```

Example: <br>
**content type** <br> application/json

```
{ 

"code": 200,
"message": "string",
- "data": {
"_id": "6137d69b21d3c78fc9a84bdf",
"name": "HNG",
"creator_email": "hng@email.com",
"creator_id": "6137d69b21d3c78fc9a84bdf",
"logo_url": "hng.zuri.chat",
"created_at": "2019-08-24",
"deleted_at": "2019-08-24",
+ "organization_settings": {...}
}

}
```
For 4xx and 5xx the interger code error and string message with be displayed.

# Update Organization Name

## Authorization 
### End-Point 
<details>
<summary> PATCH/organizations </summary>
Zuri Chat Core API

https://api.zuri.chat/organizations/{organization_id}/name

</details>


### Request Sample
**content type** <br> application/json

```
{ 

"organization_name": "hngworkspace"

}
```

 ## Response
 ### **200** Successfully updated the resource
**RESPONSE SCHEMA:** application/json

  ```
code required            integer<int32>
message required         string
```
## Response Sample
**content type** <br> application/json

```
{ 

"code": 200,
"message": "resource updated successfully"

}

```

# Update Organization Logo
Adding or changing a verified organization logo.
### End-Point 
<details>
<summary> PATCH/organizations </summary>
Zuri Chat Core API

https://api.zuri.chat/organizations/{organization_id}/logo

</details>

### **Request Sample**
**content type** <br> application/json
 
  ```
{ 

"url": "https://image.storage/image.png"

}

```

## Response
**200** Successfully updated the resource

```
RESPONSE SCHEMA:         Application/json
code required            integer<int32>
message required         string
```
## Response Sample
**content type** <br> application/json

```
{ 

"code": 200,
"message": "resource updated successfully"

}

```





## Standard Error Responses 
The Authentication API may return the following HTTP Status Codes:

---

### **400** Bad Request, e.g wrong user id <br>

```
RESPONSE SCHEMA: application/json

code required      integer <int32> 
message required   string

 ```


### **401** Access token is missing or invalid <br>

```
 RESPONSE SCHEMA:   application/json

code required        integer <int32>
message required     string


```

 ### **422** Server unable to process contained information e.g API behavior <br>

```
RESPONSE SCHEMA: application/json

code required      integer <int32> 
message required   string 

```

### **500** Internal server error occured during operation

```

RESPONSE SCHEMA:     application/json

code required         integer <int32>
message required      string

```