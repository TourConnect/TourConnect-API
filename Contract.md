TourConnect Integrations API
=============================

## Contracts

### Contract resource

Depending on the contract type the contract resource will only have either the accomodation or non accomodation contract part populated.

See the JSON definition of an accomodation type of contract resource here:
https://github.com/TourConnect/TourConnect-API/blob/master/JSON/accomodationContract.json

See the XML definition of a non accomodation contract resource here:
https://github.com/TourConnect/TourConnect-API/blob/master/XML/nonAccomodationContract.xml

### Retrieving a collection of contracts

```
GET /contracts[.format]
	?startdate=yyyy-mm-dd
	&enddate=yyyy-mm-dd
	&supplierid=nnn
	&new=yes_or_NO
	&pagesize=s
	&page=p
```

* **startdate** - Filter for contracts signed on or after the value. No start date limit if omitted.
* **enddate** - Filter for contracts signed on or before the value. No end date limit if omitted.
* **supplierid** - Filter on contracts for a particular supplier only. Contracts for all suppliers if omitted.
* **new** - Whether to filter for those contracts only that have not been retrieved before. Do not filter contracts if omitted.
* **pagesize** - Retrieving only up to the pagesize number of results at a time. Retrieve all at once if omitted.
* **page** - Retrieving the page . First page if omitted.

All query parameters are optional.

The request returns a collection of accomodation contracts. (See definition of collection and accomodation contract.) For example:

Collection in JSON format without an envelope:
https://github.com/TourConnect/TourConnect-API/blob/master/JSON/contractCollection.json

Collection in XML format with an envelope:
https://github.com/TourConnect/TourConnect-API/blob/master/XML/contractCollectionEnvelope.xml

The corresponding generated XSD:
https://github.com/TourConnect/TourConnect-API/blob/master/XSD/contractCollectionEnvelope.xsd

## Back to ReadMe
https://github.com/TourConnect/TourConnect-API/blob/master/README.md