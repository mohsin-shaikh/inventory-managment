# Inventory Management System

This is a model which supports many aspects,

Supports Sites, Locations and Warehouses etc.
Supports Categorization and Grouping
Support Generic Product (Ex. "Table Clock" and specific product "Citizen C123 Multi Alarm Clock" )
Also support Brand Variants (by various manufacturers)
Has CSM (color / size / model support) Ex. Bata Sandles (Color 45 Inch Blue color)
Product Instances with serials (such as TVs , Refrigerators etc.)
Lot control / Batch control with serial numbers.
Pack Size / UOM and UOM Conversion
Manufacturer and Brands as well as Suppliers
Also included example transaction table (Purchase order)
There are many other transaction types such as Issues, Transfers, Adjustments etc.
Hope this would help. Please let me know if you need further information on each table.

### Sites
id
site_code
Site_name

### Warehouse
id
site_id
warehouse_code
warehouse_name

### Item Category
id
category_code
category_name

### Item Group
id
group_code
group_name

### Generic Product
id
generic_name

### Product
id
product_code
category_id
group_id
brand_id
generic_id
model_id/part_id
product_name
product_description
product_price (current rate)
has_instances(y/n)
has_lots (y/n)
has_attributes
default_uom
pack_size
average_cost
single_unit_product_code (for packs)
dimension_group (pointing to dimensions)
lot_information
warranty_terms (general not specific)
is_active
deleted

### product attribute type (color/size etc.)
id
attribute_name

### product_attribute
id
product_id
attribute_id

### product attribute value (this product -> red)
id
product_attribute_id
value

### product_instance
id
product_id
instance_name (as given by manufacturer)
serial_number
brand_id (is this brand)
stock_id (stock record pointing qih, location etc.)
lot_information (lot_id)
warranty_terms
product attribute value id (if applicable)

### product lot
id
lot_code/batch_code
date_manufactured
date_expiry
product attribute value id (if applicable)

### Brand
id
manufacturer_id
brand_code
brand_name

### Brand Manufacturer
id
manufacturer_name

## Stock
id
product_id
warehouse_id, zone_id, level_id, rack_id etc.
quantity in hand
product attribute value id (if applicable) [we have 4 red color items etc.]
Product Price Records
product_id
from_date
product_price

### Purchase Order Header
id
supplier_id
purchase_date
total_amount

### Purchase Order Line
id
po_id
product_id
unit_price
quantity

### Supplier
id
supplier_code
supplier_name
supplier_type

### product_uom
id
uom_name

### product_uom_conversion
id
from_uom_id
to_uom_id
conversion_rule
