HTTP REQ COMPONENTS
	resource URI (endpoint)
	headers - each resource contain headers - metadeta with api request and response, helps with tracing issues
	auth - getting access to resource
{queryparam}	body - when post,put,patch used; resource to be created/edited

{base uri}{host_url}https://example/com{host_url}/userapi/v1{base uri}/{resource}users{resource}?{queryparam}email=something@.com{queryparam}
