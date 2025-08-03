# Backend of fraud checker extension

Mind Map: https://miro.com/app/board/uXjVL0EDStU=/?lid=bteej2r6fzsw

## APIS:

1. https://host:port/api/v1/website/check?name=https://example.com [GET]
2. https://host:port/api/v1/website/review [POST]

API 2: http://localhost:5003/api/v1/website/review

Body:

```
{
    "reviewMessage": "The website is beautiful, but the quality of their clothes is not good.",
    "siteId": "677bdcdad3ad95823e4eda0b",
    "feedback": {
        "ProductQuality": [
            {
                "name": "Durability",
                "baseRating": 4
            },
            {
                "name": "Overall Quality",
                "baseRating": 1
            }
        ],
        "CustomerServices": [
            {
                "name": "Responsiveness",
                "baseRating": 5
            },
            {
                "name": "Friendliness",
                "baseRating": 4
            }
        ],
        "PlatformExperience": [
            {
                "name": "Ease of Use",
                "baseRating": 5
            },
            {
                "name": "Design",
                "baseRating": 4
            }
        ]
    }
}
```

Will Calculate user feedback rating

Console log:

```sh
Example app listening on port 5003
Body {
  reviewMessage: 'website ta sundor kinto tader kaporer man valo na',
  siteId: '6771561d8ea2cd28cb5e86a3',
  feedback: {
    ProductQuality: [ [Object], [Object], [Object] ],
    CustomerServices: [ [Object], [Object], [Object] ],
    PlatformExperience: [ [Object], [Object], [Object] ]
  }
}
Website Data {
  _id: new ObjectId('6771561d8ea2cd28cb5e86a3'),
  websiteName: 'https://example.com',
  verified: true,
  reviewId: [ 'review1', 'review2', 'review3' ],
  rating: 4.5
}
feedback rating 3.82
```
