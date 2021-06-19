# README

## users テーブル

| Column             | Type    | Option       |
| ------------------ | ------- | ------------ |
| nickname           | string  | null: false  |
| email              | string  | unique: true |
| encrypted_password | string  | null: false  |
| name               | string  | null: false  |
| name_kana          | string  | null: false  |
| birthday           | integer | null: false  |

### Association

- has_many :items
- has_many :purchase_managements

## items テーブル

| Column            | Type       | Option            |
| ----------------- | ---------- | ----------------- |
| text              | text       | null: false       |
| price             | integer    | null: false       |
| user              | references | foreign_key: true | 
| category          | string     | null: false       |
| product condition | integer    | null: false       |
| shipping charges  | string     | null: false       |
| shipment source   | string     | null: false       |
| date of shipment  | string     | null: false       |

### Association

- belongs_to :user
- has_one :items

## purchase_managements テーブル

| Column | Type       | Option            |
| ------ | ---------- | ----------------- |
| user   | references | foreign_key: true |
| item   | references | foreign_key: true |

### Association

- belongs_to :item
- belongs_to :user
- has_one :shipping_addresses

## shipping_addresses テーブル

| Column              | Type       | Option            |
| ------------------- | ---------- | ----------------- |
| postal_code         | string     | null: false       |
| prefecture          | string     | null: false       |
| municipality        | string     | null: false       |
| address             | string     | null: false       |
| building_name       | string     | null: false       |
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
