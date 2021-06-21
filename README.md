# README

## users テーブル

| Column             | Type   | Option                    |
| ------------------ | ------ | ------------------------- |
| nickname           | string | null: false               |
| email              | string | unique: true, null: false |
| encrypted_password | string | null: false               |
| last_name          | string | null: false               |
| first_name         | string | null: false               |
| last_name_kana     | string | null: false               |
| first_name_kana    | string | null: false               |
| birthday           | date   | null: false               |

### Association

- has_many :items
- has_many :purchase_managements

## items テーブル

| Column               | Type       | Option            |
| -------------------- | ---------- | ----------------- |
| product_name         | string     | null: false       |
| product_description  | text       | null: false       |
| price                | integer    | null: false       |
| user                 | references | foreign_key: true | 
| category_id          | string     | null: false       |
| product_condition_id | string     | null: false       |
| shipping_charge_id   | string     | null: false       |
| shipment_source_id   | string     | null: false       |
| date_of_shipment_id  | integer    | null: false       |

### Association

- belongs_to :user
- has_one :purchase_management

## purchase_managements テーブル

| Column | Type       | Option            |
| ------ | ---------- | ----------------- |
| user   | references | foreign_key: true |
| item   | references | foreign_key: true |

### Association

- belongs_to :item
- belongs_to :user
- has_one :shipping_address

## shipping_addresses テーブル

| Column              | Type       | Option            |
| ------------------- | ---------- | ----------------- |
| postal_code         | string     | null: false       |
| prefecture          | string     | null: false       |
| municipality        | string     | null: false       |
| address             | string     | null: false       |
| building_name       | string     |                   |
| phone_number        | string     | null: false       |
| purchase_management | references | foreign_key: true |

### Association

- belongs_to : purchase_management





This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
