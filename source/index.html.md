---
title: SynQ Video API 1.0.5

search: true
---

# SynQ Video API 1.0.5
> ### Produces


## Find videos matching some metadata criteria.

	
```http
HTTP/1.1 200 OK
Content-Type: application/json

"object"
```
```http
HTTP/1.1 400 Bad Request
```

You may optionally request only some of the metadata fields.


### Parameters
Name | In | Type | Description
--- | --- | --- | ---
api_key<b title="required">&nbsp;*&nbsp;</b> | formData | string | 
metadata<b title="required">&nbsp;*&nbsp;</b> | formData | string | 
keys | formData | string | Optional. 

### Responses
Http code | Type | Description
--- | --- | ---
200 | object | An array of video metadata objects, containing some or all of the videos fields.
400 | no content | invalid input


## Create a new video with optional metadata.

	
```http
HTTP/1.1 200 OK
Content-Type: application/json

"object"
```
```http
HTTP/1.1 400 Bad Request
```

You may optionally add some metadata about the video. Any metadata field whose key starts with an underscore (_) may be assigned an arbitrary string value. The other fields have special meaning and constrains. See the metadata_object for more information.


### Parameters
Name | In | Type | Description
--- | --- | --- | ---
api_key<b title="required">&nbsp;*&nbsp;</b> | formData | string | 
metadata | formData | string | Optional. 

### Responses
Http code | Type | Description
--- | --- | ---
200 | object | A video object, containing all metadata members.
400 | no content | An error occurred


## Return details about a video.

	
```http
HTTP/1.1 200 OK
Content-Type: application/json

"object"
```
```http
HTTP/1.1 400 Bad Request
```

You may optionally request only some of the metadata fields.


### Parameters
Name | In | Type | Description
--- | --- | --- | ---
api_key<b title="required">&nbsp;*&nbsp;</b> | formData | string | 
video<b title="required">&nbsp;*&nbsp;</b> | formData | string | 
keys | formData | string | Optional. 

### Responses
Http code | Type | Description
--- | --- | ---
200 | object | A video metadata object, containing some or all of the video’s fields.
400 | no content | invalid input


## Update a video&#039;s metadata.

	
```http
HTTP/1.1 200 OK
```
```http
HTTP/1.1 400 Bad Request
Content-Type: application/json

"string"
```

Any metadata field whose key starts with an underscore (_) may be assigned an arbitrary string value. The other fields have special meaning and constrains. See the metadata_object for more information.


### Parameters
Name | In | Type | Description
--- | --- | --- | ---
api_key<b title="required">&nbsp;*&nbsp;</b> | formData | string | 
video<b title="required">&nbsp;*&nbsp;</b> | formData | string | 
metadata | formData | string | Optional. 

### Responses
Http code | Type | Description
--- | --- | ---
200 | no content | A video object, containing all metadata members.
400 | string | An error occurred


## Return parameters needed for uploading a video file.

	
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "AWSAccessKeyId": "string",
    "Content-Type": "string",
    "Policy": "string",
    "Signature": "string",
    "acl": "string",
    "key": "string"
}
```
```http
HTTP/1.1 400 Bad Request
```

Return parameters needed for uploading a video file to Amazon Simple Storage Service. See http://docs.aws.amazon.com/AmazonS3/latest/API/sigv4-post-example.html


### Parameters
Name | In | Type | Description
--- | --- | --- | ---
api_key<b title="required">&nbsp;*&nbsp;</b> | formData | string | 
video<b title="required">&nbsp;*&nbsp;</b> | formData | string | 

### Responses
Http code | Type | Description
--- | --- | ---
200 | object | A video object, containing all metadata members.
400 | no content | An error occurred


## Return parameters needed for transmitting a video stream to our rtmp receiver.

	
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "rtmp_host": "string",
    "rtmp_port": "string",
    "rtmp_key": "string",
    "rtmp_url": "string"
}
```
```http
HTTP/1.1 400 Bad Request
```

### Parameters
Name | In | Type | Description
--- | --- | --- | ---
api_key<b title="required">&nbsp;*&nbsp;</b> | formData | string | 
video<b title="required">&nbsp;*&nbsp;</b> | formData | string | 

### Responses
Http code | Type | Description
--- | --- | ---
200 | object | Returns an object containing the information required to stream to our RTMP receiver.
400 | no content | An error occurred



# Models
