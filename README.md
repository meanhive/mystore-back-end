# mystore-back-end
mystore back end using nodejs, express and mongoDB

Admin Credential APIs
-------------------------------------

Admin Signup 
-------------------------------------
Request Type : POST
API : http://localhost:2019/admin/signup
Request Body Example : (JSON) 
{
        firstName:  'Rizwan',
        lastName: 'Khan',
        email: 'rizwankhan@gmail.com',
        password: '12345'
}

Admin Login
--------------------------------------
Request Type: POST
API: http://localhost:2019/admin/login
Request Body Example: (JSON)
{
        email: 'rizwankhan@gmail.com',
        password: '12345'
}

Response : {
        message: 'Login Successfully',
        token: xxxxxxxxxxxxxxxxxxxxxxxx
}

Add New Product
--------------------------------------
Request Type: POST,
API: http://localhost:2019/products/create
Request Body Example JSON {
        name: 'Red t shirt in check',
        price: 21,
        stock: 100,
        description: 'Its a very good t shirt',
        productPic: [
                {img: http://domain.com/red-shirt.jpeg}
        ],
        keyword: 'red t shirt check t shirt',
        category: xxxxxcategoryIdxxxxxxxxxxxxxxxxxx,
        createdBy: xxxxxxxxxxxxxxadminIdxxxxxxxxxx
}
Response Example : {
        message: {}
}

Get Product List
-----------------------------------------
Request Type: GET,
API : http://localhost:2019/products
Response : [
        {
                _id: xxxxxxxxxxxxxxxx,
                name: xxxxxxxx,
                price: xxxxxxx,
                productPic: [
                        {img: xxxxxxxxxxxx.jpeg}
                        {img: yyyyyyyyyy.png}
                ]
                slug: xxxxxxxxxxxxx
        },
        {
                _id: xxxxxxxxxxxxxxxx,
                name: xxxxxxxx,
                price: xxxxxxx,
                productPic: [
                        {img: xxxxxxxxxxxx.jpeg}
                        {img: yyyyyyyyyy.png}
                ]
                slug: xxxxxxxxxxxxx
        }
]

Add New category
--------------------------------------
Request Type: POST
API: http://localhost:2019/category
Request Body Example : {
        name: xxxxxxxxxxxxx,
        slug: xxxxxxxxx,
        parent: xxxxxxxxxxxxxx, or empty
        createdBy: xxxxxxxxxxxxx
}


Get Category List
Request Type: GET,
API: http://localhost:2019/category
Response {
    "message": [
        {
            "_id": "5d8bc1b41e90af2f94e252dd",
            "name": "Accessories",
            "slug": "accessories",
            "children": [
                {
                    "_id": "5d8bc7fc1e90af2f94e252de",
                    "name": "Handbags",
                    "slug": "handbags",
                    "children": []
                },
                {
                    "_id": "5d8bc8df4c53543868bfcd14",
                    "name": "Watches",
                    "slug": "watches",
                    "children": []
                }
            ]
        }
    ]
}
