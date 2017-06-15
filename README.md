## Fashion eCommerce Platform DB Schema
The following schema represents the DB :postbox: of an eCommerce :moneybag: platform where businesses/brands can create stores to sell their fashion :dress: :mans_shoe: :handbag: products. You can always "panel beat" the schema to suit your needs if that's not where you're headed! :red_car: To contribute: **fork this repo and send a pull request**.

**NB: pk = *primary key*, fk = *foreign key***

### :high_heel: products
* id (pk)
* ref (reference, *unique*)
* name
* description
* category_id (fk)
* store_id (fk)
* cost_price
* selling_price
* size
* color
* weight
* sales_count
* created_at (*date*)
* updated_at (*date*)

### :camera: product_images
* id (pk)
* product_id (fk)
* image_url
* created_at (*date*)
* updated_at (*date*)

### :eight_spoked_asterisk: categories
* id (pk)
* slug
* name
* description
* display_image_url
* created_at (*date*)
* updated_at (*date*)

### :family: users
* id (pk)
* ref (reference, *unique*)
* name
* email
* password
* phone
* address
* role (e.g customer, dispatch, manager, admin etc)
* created_at (*date*)
* updated_at (*date*)

### :department_store: stores
* id (pk)
* name
* description
* display_image_url
* logo_image_url
* slug
* created_at
* updated_at

### :briefcase: orders
* id (pk)
* ref (reference, *unique*)
* user_id (fk)
* status (e.g pending, processing, cancelled, delivered)
* created_at (*date*)
* updated_at (*date*)

### :jeans: ordered_items
* id (pk)
* order_id
* product_id
* quantity
* cost_per_unit (*price unit product was sold for*)

### :bookmark: tags
* id (pk)
* slug
* name
* created_at (*date*)
* updated_at (*date*)


### :raised_hands: cart
* id (pk)
* user_id (fk)
* product_id (fk)
* quantity
* created_at (*date*)
* updated_at (*date*)

### :heart_eyes: wishlists
* id (pk)
* user_id (fk)
* product_id (fk)
* created_at (*date*)
* updated_at (*date*)

### :ticket: coupons
* id (pk)
* code
* description
* discount_type (e.g percentage, monetary value, fraction etc)
* discount (*number*)
* min_order_type (e.g number of products, quantity of products, order cost etc)
* min_order (minimum order, *number*)
* expires (*date*)
* created_at (*date*)
* updated_at (*date*)

### :pencil: product_reviews
* id (pk)
* user_id (fk)
* product_id (fk)
* remarks
* rating (e.g 0-5)
* created_at (*date*)
* updated_at (*date*)