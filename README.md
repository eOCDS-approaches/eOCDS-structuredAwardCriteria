# Criteria

Set of criteria may include different types of requirements, used in different way and for the different reasons. Moreover, some of used criteria may be prescribed by the legal basis “by default” (exclusion grounds of ESPD or particular chapters of selection grounds from ESPD, like General yearly turnover). 

## Types of criteria

Under each Contracting Process Procuring Entity may define and apply a various types of criteria for the scoring function. These different types are following:

**Exclusion grounds** - group of these criteria are eligibility criteria put forward by the Procuring Entity to the candidates - all of them are published in the Contract Notice and relate to the whole procedure.

**Selection criteria and minimum qualification requirements** - group of these criteria is also eligibility criteria, but it is optional for the Procuring Organization to apply for the tender. The criteria allow determining the quantitative and qualitative criteria for candidates for participation in the procedure.

**Allowances**
The group of these criteria is the award criteria and should be taken into account by the Procuring Organization in cases determined by the relevant law, which also defines a set of such criteria and their values. Examples include the following criteria:

- The proposal of the candidate-resident of the country of jurisdiction receives a reduction factor 
- The proposal of a candidate-resident of the country of jurisdiction if such candidate is an organization in the category of SMEs receives a reduction factor of price.

**Non-price criteria**
The group of these criteria is the award criteria and can be applied by the PEn in the case of the Most Economic Advantages Tender strategy. MEAT is recognized as winning according to the following criteria:

- in case of contracts for public procurement of goods - the price, delivery time, payment terms, profitability, quality, aesthetic, functional and technical characteristics, capabilities and cost of technical assistance and maintenance;
- in the case of contracts for public procurement of works - the proposed quality, the cost per unit of product of the bidder by the end of the work, the total price, the experience of the bidder, etc. The share of the price in the total evaluation of the offers should not be less than 80 per cent;
- in the case of contracts for public procurement of services - the proposed quality, the cost per unit of the offeror’s products, the total price, the experience of the bidder, etc. The price share in the total evaluation of the offers should not be less than 40 per cent.

So depending on the category of procurement, the PE can determine a set of non-price criteria (quantitative and qualitative) in the range of 20-60%, which will be taken into account along with the price part of the offer and affect the absolute economic value of the entire tender proposal of the participant, increasing his chances to win the tender,  do not lower the price (suggesting the most favorable economic conditions). 

## Criterion values

Each of described requirements may or may not be associated with a set of available values. For example, Exclusion Grounds and Allowances available as ‘true/false’ flags and no other options. And Selection or Non-price criteria usually contains not only default or minimum requirements but also other values, available for the tenderers’ choice. Where this is the case, Procuring Entity obliged to specify in advance:

- features, the values for which will be the subject of electronic auction, provided that such features are quantifiable and can be expressed in figures or percentages
- any limits on the values which may be submitted, as they result from the specifications relating to the subject of the contract  

## Example

Below is an example of requirements specified against both an item and a tenderer:

```json
{
  "tender": {
    "items": [
      {
        "id": "001",
        "quantity": 10
      },
      {
        "id": "002",
        "quantity": 10
      }
    ],
    "criteria": [
      {
        "id": "002",
        "title": "Service warranty",
        "description": "A minimum product warranty of 1 year is required",
        "source": "tenderer",
        "relatesTo": "item",
        "relatedItem": "001",
        "requirementGroups": [
          {
            "id": "002-1",
            "requirements": [
              {
                "id": "002-1-1",
                "title": "A minimum warranty of 1 year is guaranteed",
                "dataType": "boolean",
                "expectednValue": true
              },
              {
                "id": "002-1-2",
                "title": "The number of years for proposed warranty",
                "dataType": "integer",
                "minValue": 1,
                "maxValue": 3
              }
            ]
          }
        ]
      },
      {
        "id": "003",
        "title": "Capacity",
        "description": "Minimum qualification requirements",
        "source": "tenderer",
        "relatesTo": "tenderer",
        "requirementGroups": [
          {
            "id": "003-1",
            "requirements": [
              {
                "id": "003-1-1",
                "title": "At least one Google-certified specialist on-board",
                "dataType": "boolean",
                "expectedValue": true
              },
              {
                "id": "003-1-2",
                "title": "Number of Google-certified staff",
                "description": "",
                "dataType": "integer",
                "minValue": 1,
                "maxValue": 5
              }
            ]
          }
        ]
      }
    ]
  }
}
```
