TourConnect Integrations API
=============================

This documentation provides basic instructions for a Contractor on how to programmatically access signed contracts on the TourConnect platform.  You will need a live TourConnect account and at least one signed test or live contract available for download.

## API Endpoint

The base Url for the TourConnect Rest API starts at

```
https://api.tourconnect.com/v[version]/
```

We maintain multiple versions of the API. The current version is 1.

Please note: for simplicity throughout the remainder of the document, we will omit the base Url from an actual endpoint discussed.

## Access and Authentication

To have acces to the TourConnect API, you will need the following:

* **ContractorID** - This is your Contractor name and it is displayed at the top left of your dashboard after login.

* **API Key** -  This is available within your TourConnect profile.  To locate this key, login to your account and then scroll down to the bottom of the 'Profile' page where you would see the value for your 'API Key'.

The TourConnect API uses basic authentication using the ContractorID as the login ID and API Key as the password for credentials. Simply add the the authentication header on the request generated from this pair.

## API Response

### Response format

The TourConnect API can serve up a response in **JSON** or **XML** format. The default format is JSON. You can specify the requested format the following way:

```
https://api.tourconnect.com/v1/contracts

https://api.tourconnect.com/v1/contracts.json

https://api.tourconnect.com/v1/contracts.xml
```

### Response object

The response will be returned with or without an envelope depending on the way requested. By default for JSON format the response is returned without an envelope. For XML format by default the response is returned with an envelope.

```
https://api.tourconnect.com/v1/contracts.xml?envelope=true

https://api.tourconnect.com/v1/contracts.json?envelope=false
```

If requested with an envelope the response will contain the result of the request and the actual data returned as separate objects. The result contains of a status code, an error code and a description. The data depends on the type of object returned.

```
{
	result: {
		statusCode: 200,
		returnCode: 0,
		returnMessage: "Success"
	},
	data: {
		contractId: "4244240",
		...
	}
}
```

If the data is requested without an envelope then if the request was successfull, only the data object is returned. 

```
{
	contractId: "4244240",
	...
}
```

If the request failed only the result part is returned. 

```
{
	statusCode: 400,
	returnCode: 40001,
	returnMessage: "Invalid API version"
}
```

### Status Codes

Please refer to the following table for the list of standard HTTP status codes returned.

| Status Code  | Reason |
| ------------- | :------------- |
|200 | OK 
|400 | Bad Request 
|401 | Not Authorized 
|404 | Not Found 
|500 | Internal Server Error 
|503 | Service Unavailable 

### Return Codes

Please refer to the following table for the list of return codes and their associated reason.

| Return Code  | Reason |
| ------------- | :------------- |
|0 | Success 
|40001 | Invalid API Version 
|40002 | Invalid SupplierID 
|40003 | Invalid Date format. Please specify date as yyyy-mm-dd 
|40004 | Invalid Date Range 
|40005 | Invalid arguments... 
|40101 | Invalid API Key 
|40102 | Invalid Contractor ID 

### Collection paging

Collections can be accessed in a paged format. Additional query parameters in the request define how many records a result page should contain and which page is requested. If omitted all records in the collection are returned.

```
/contracts?pageSize=3&page=1
```
The response contains the objects in an array along with the URL for the next and previous page of data and the total number of objects available in the entire collection.

```
{
	resultCount: 147,
	items: [
		{...},
		{...},
		{...}
	],
	prevPageUrl: '',
	nextPageUrl: '/contracts?pageSize=3&page=2'
}
```

## Contracts

You can retrieve accomodation or non accomodation contracts separately or all contracts alltogether.

### All Contracts

See details about contracts here:
https://github.com/TourConnect/TourConnect-API/blob/master/Contract.md

### Accomodation Contracts

See details about accomodation contracts here:
https://github.com/TourConnect/TourConnect-API/blob/master/AccomodationContract.md

### Non-Accomodation Contracts

See details about non-accomodation contracts here:
https://github.com/TourConnect/TourConnect-API/blob/master/NonAccomodationContract.md

## Questions?

If you have questions, suggestions or any issues, please feel free to send us a note on: http://helpdesk.tourconnect.com We will get back to you as soon as possible!
