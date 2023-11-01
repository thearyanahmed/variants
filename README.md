# variants

I understand now. Thank you for clarifying. In that case, you'll need to modify the schema to have separate rows for each option. Here's the updated schema:

**Table: products**

| Column     | Type          | Constraints           |
|------------|---------------|----------------------|
| id         | INT           | PRIMARY KEY, AUTO_INC |
| name       | VARCHAR(255)  | NOT NULL             |

**Table: attributes**

| Column       | Type          | Constraints                     |
|--------------|---------------|--------------------------------|
| id           | INT           | PRIMARY KEY, AUTO_INC           |
| product_id   | INT           | NOT NULL, FOREIGN KEY(products) |
| name         | VARCHAR(255)  | NOT NULL                       |

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
| attribute_id   | INT           | NOT NULL, FOREIGN KEY(attributes)          |
| option_id      | INT           | NOT NULL, FOREIGN KEY(options)             |

This schema allows each option to have its own row in the `options` table, which is linked to the `attributes` table. The `variations` table references the options through the `option_id`.
