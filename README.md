# README

## users テーブル

| Column             | Type   | Option       |
| ------------------ | -------| ------------ |
| name               | string | NOT NULL     |
| email              | string | unique: true |
| encrypted_password | string | NOT NULL     |

### Association

- has_many :items
- has_many :purchase_managements

## items テーブル

| Column   | Type       | Option            |
| -------- | ---------- | ----------------- |
| text     | text       | NOT NULL          |
| category | string     | NOT NULL          |
| price    | integer    | NOT NULL          |
| user     | references | foreign_key: true |

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

| Column               | Type         | Option            |
| -------------------- | ------------ | ----------------- |
| postal_code          | integer      | NOT NULL          |
| adress               | string       | NOT NULL          |
| phone_number         | varchar(255) | NOT NULL          |
| purchase_managements | references   | foreign_key: true |

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
