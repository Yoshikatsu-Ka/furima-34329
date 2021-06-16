# README

## users テーブル

| Column   | Type    | Option   |
| -------- | --------| -------- |
|name      | string  | NOT NULL |
|email     | string  | NOT NULL |
|password  | string  | NOT NULL |

### Association

- has_many :items
- has_many :comments

## items テーブル

| Column   | Type       | Option   |
| -------- | ---------- | -------- |
| text     | text       | NOT NULL |
| image    |            |          |
| category | string     | NOT NULL |
| price    | integer    | NOT NULL |
| user_id  | references |          |

### Association

- belongs_to :users
- has_many :comments

## comments テーブル

| Column       | Type       | Option   |
| ------------ | ---------- | -------- |
| comment_text | text       | NOT NULL |
| user_id      | references |          |
| item_id      | references |          |

### Association

- belongs_to :users
- belongs_to :items




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
