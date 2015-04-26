TourConnect Integrations API
=============================

## Accomodation Contracts

### Accomodation contract resource

See the JSON definition of the accomodation contract resource here:
https://github.com/TourConnect/integrations/blob/master/JSON/accomodationContract.json

See the XML definition of the accomodation contract resource here:
https://github.com/TourConnect/integrations/blob/master/XML/accomodationContract.xml

### Retrieving a collection of accomodation contracts

```
GET /contracts/accomodation[.format]
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
https://github.com/TourConnect/integrations/blob/master/JSON/accomodationContractCollection.json

Collection in XML format with an envelope:
https://github.com/TourConnect/integrations/blob/master/XML/accomodationContractCollectionEnvelope.xml

The corresponding generated XSD:
https://github.com/TourConnect/integrations/blob/master/XSD/accomodationContractCollectionEnvelope.xsd

## Back to ReadMe
https://github.com/TourConnect/integrations/blob/master/README.md