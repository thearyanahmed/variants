# variants

**Table: products**

| Column     | Type          | Constraints           |
|------------|---------------|----------------------|
| id         | INT           | PRIMARY KEY, AUTO_INC |
| name       | VARCHAR(255)  | NOT NULL             |

**Table: attributes**

| Column       | Type          | Constraints                     |
|--------------|---------------|---------------------------------|
| id           | INT           | PRIMARY KEY, AUTO_INC           |
| name         | VARCHAR(255)  | NOT NULL                        |

**Table: options**

| Column       | Type          | Constraints                     |
|--------------|---------------|--------------------------------|
| id           | INT           | PRIMARY KEY, AUTO_INC           |
| attribute_id | INT           | NOT NULL, FOREIGN KEY(attributes) |
| value        | VARCHAR(255)  | NOT NULL                       |

**Table: variations**

| Column         | Type          | Constraints                                |
|----------------|---------------|-------------------------------------------|
| id             | INT           | PRIMARY KEY, AUTO_INC                      |
| product_id     | INT           | NOT NULL, FOREIGN KEY(products)            |
| ~option_id~      | INT           | NOT NULL, FOREIGN KEY(options)             |
| stock      | INT           | NOT NULL, FOREIGN KEY(options)             |

**Table: variation combinations**

| product_id       |option_id | variant_id  |
|----------------|-------------------------|--------------------|
| tShirt   | Red       | 1 |
| tShirt   | L         | 1 |       
| tShirt   | Male      | 1 |
| tShirt   | Red       | 2 |
| tShirt   | L         | 2 |
| tShirt   | Female    | 2 |
| tShirt   | Blue      | 3 |
| tShirt   | L         | 3 |       
| tShirt   | Male      | 3 |
| tShirt   | Blue      | 4 |
| tShirt   | L         | 4 |
| tShirt   | Female    | 4 |
| tShirt   | Red       | 5 |
| tShirt   | M         | 5 |       
| tShirt   | Male      | 5 |
| tShirt   | Red       | 6 |
| tShirt   | M         | 6 |
| tShirt   | Female    | 6 |
| tShirt   | Blue      | 7 |
| tShirt   | M         | 7 |       
| tShirt   | Male      | 7 |
| tShirt   | Blue      | 8 |
| tShirt   | M         | 8 |
| tShirt   | Female    | 8 |

## Demo
variations

| product_id       | stock  | id |
|-------------------|---------------|--------------------|
| tShirt   | 10       | 1 |
| tShirt   | 20         | 2 |       
| tShirt   | 30         | 3 |
| tShirt   | 40    | 4 |
| tShirt   | 50       | 5 |
| tShirt   | 60         | 6 |       
| tShirt   | 70         | 7 |
| tShirt   | 80    | 8 |

** Display table** _(not db table)_


| product       | variation option (1) | varianation option (2) | variation option (3)  | variant id | stock |
|----------------|---------|----------------|--------------|------| ---- |
| tShirt   | Red    | L | Male       | 1 | 10 |
| tShirt   | Red    | L | Female     | 2 | 20 |
| tShirt   | Blue   | L | Male       | 3 | 30 |
| tShirt   | Blue   | L | Female     | 4 | 40 |
| tShirt   | Red    | M | Male       | 5 | 50 |
| tShirt   | Red    | M | Female     | 6 | 60 |
| tShirt   | Blue   | M | Male       | 7 | 70 |
| tShirt   | Blue   | M | Female     | 8 | 80 |



