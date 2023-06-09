<!DOCTYPE xmd>


# LunchInfo developer documentation
## What is LunchInfo and how does it work?
- This was a C# WPF application, that I wrote back in Summer 2019 at my summer job. It's purpose was simple: Create a centralized app, that can display the current menu, you can order from it for the next week (you're not directly place an order, but rather you'll be added to the order form, that company IT will send to the specified restaurant).
- You can optionally see an actual image of a food, that was actually ordered previously.
- You can also see today's menu, if you ordered last week.
- It could've been developed as a website, but I wasn't done it that way, so here is the chance to do it that way, since I wanted to rewrite it, so the opportunity came to do it so.

## Client-server communication

]>info< ### List your orders
] - Endpoint: `/v1/orders`
] - Auth: oauth (bearer token from AAD)
] - Request: `null`
] - Response: 
] ```json
] {
]     "orders": [
]         {
]             "id": 0,
]             "restaurant": "Finom Étel Kft.",
]             "date": "2023-06-02T11:34:42",
]             "order_date": "2023-06-09T17:00:00",
]             "appetizer": "",
]             "soup": "",
]             "main_course": "",
]             "dessert": "",
]             "price": 1970,
]             "price_currency": "HUF",
]             "payment_method": "SZEP Card",
]         },
]         {
]             "id": 0,
]             "restaurant": "Finom Étel Kft.",
]             "date": "2023-06-02T11:34:45",
]             "order_date": "2023-06-09T17:00:00",
]             "appetizer": null,
]             "soup": "Húsleves gazdagon", // retrieved from courses table by id 5
]             "main_course": "", // retrieved from courses table by id 123
]             "dessert": "Ízes bukta", // retrieved from courses table by id 107
]             "price": 2020,
]             "price_currency": "HUF",
]             "payment_method": "SZEP Card",
]         }
]     ]
] }
] ```
