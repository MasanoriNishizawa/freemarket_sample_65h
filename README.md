# README

**establish database**

## Users Table
|Column|Type|Options|
|------|----|-------|
|id|integer||
|nickname|string|null: false|
|password|string|null :false|
|email|string|null: false|
|name|string|null: false|
|name_kana|string|null: false|
|birth|integer|null: false|
|tell|integer|null: false|
|profit|integer|null: false|
### Association
- has_many :items
- has_one :address


## Addresses Table
|Column|Type|Options|
|------|----|-------|
|id|integer||
|postal_code|integer|null: false|
|prefectures|integer|null: false|
|municipality|string|null: false|
|house_number|string|null: false|
|building|string||
|user_id|references|null: false, foreign_key: true|

### Association
- belongs_to :user


## Items Table
|Column|Type|Options|
|------|----|-------|
|id|integer||
|name|string|null: false|
|discription|text||
|price|integer|null: false|
|condition|integer|null: false|
|shipping_charge|integer|null: false|
|shipping_date|integer|null: false|
|prefectures|integer|null: false|
|transaction_status|integer|null: false|
|category_id|iteger|null: false, foreign_key: true|
|seller_id|references|null: false, foreign_key: true|
|buyer_id|references|foreign_key: true|
### Association
- belongs_to :user
- belongs_to :category
- has_many :item_images


## Item_images Table
|Column|Type|Options|
|------|----|-------|
|id|integer||
|image|integer||
|items_id|iteger|null: false|

### Association
- belongs_to :item


## Categories Table
|Column|Type|Options|
|------|----|-------|
|id|integer||
|name|string|null: false|
|parent_id|references|null: false, foreign_key: true|
### Association
- has_many :items
