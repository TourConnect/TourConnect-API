TourConnect Integrations API
=============================

## Non-Accomodation Contracts

### Non-Accomodation contract resource

See the JSON definition of the non-accomodation contract resource here:
https://github.com/TourConnect/integrations/blob/master/JSON/nonAccomodationContract.json

See the XML definition of the non-accomodation contract resource here:
https://github.com/TourConnect/integrations/blob/master/XML/nonAccomodationContract.xml

### Retrieving a collection of non-accomodation contracts

```
GET /contracts/nonaccomodation[.format]
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

The request returns a collection of non-accomodation contracts. (See definition of collection and non-accomodation contract.) For example:

Collection in JSON format without an envelope:
https://github.com/TourConnect/integrations/blob/master/JSON/nonAccomodationContractCollection.json

Collection in XML format with an envelope:
https://github.com/TourConnect/integrations/blob/master/XML/nonAccomodationContractCollectionEnvelope.xml

The corresponding generated XSD:
https://github.com/TourConnect/integrations/blob/master/XSD/nonAccomodationContractCollectionEnvelope.xsd

## Back to ReadMe
https://github.com/TourConnect/integrations/blob/master/README.md