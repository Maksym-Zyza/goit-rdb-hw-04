# goit-rdb-hw-04

## 3

```sql
SELECT 
  order_details.id as id,
    order_details.quantity,
  orders.id as order_id, 
    orders.date as order_date,
  customers.id as customer_id, 
    customers.name as customer_name, 
    customers.address as customer_address, 
    customers.city as customer_city, 
    customers.postal_code as customer_postal_code, 
    customers.country as customer_country, 
  products.id as product_id,
    products.name as product_name,
    products.unit as product_unit,
    products.price as product_price,
  categories.id as category_id,
    categories.name as category_name,
    categories.description as category_description,
  employees.employee_id,
    employees.last_name as employee_last_name,
    employees.first_name as employee_first_name,
    employees.birthdate as employee_birthdate,
    employees.photo as employee_photo,
    employees.notes as employee_notes,
  shippers.id as shipper_id,
    shippers.name as shipper_name,
    shippers.phone as shipper_phone,
  suppliers.id as supplier_id,
    suppliers.name as supplier_name,
    suppliers.contact as supplier_contact,
    suppliers.address as supplier_address,
    suppliers.city as supplier_city,
    suppliers.postal_code as supplier_postal_code,
    suppliers.phone as supplier_phone
FROM order_details
inner join orders on orders.id = order_details.order_id
inner join customers on customers.id = orders.customer_id
inner join products on products.id = order_details.product_id
inner join categories on categories.id = products.category_id
inner join employees on employees.employee_id = orders.employee_id
inner join shippers on shippers.id = orders.shipper_id
inner join suppliers on suppliers.id = products.supplier_id
order by id;
```

