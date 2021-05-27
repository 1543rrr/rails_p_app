# README

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
# テーブル設計

## users テーブル

| Column    | Type   | Options     |
| --------  | ------ | ----------- |
| email     | string | null: false |
| password  | string | null: false |
| name      | string | null: false |
| profile   | text   | null: false |
| music     | text   | null: false |
| musical_instrument | text   | null: false |

### Association

- has_many :posts
- has_many :comments

## posts テーブル

| Column | Type          | Options     |
| ------ | --------------| ----------- |
| title  | string        | null: false |
| catch  | text          | null: false |
| concept| text          | null: false |
| user   | references    | 

### Association

- belongs_to :user
- has_many :comments 

## comments テーブル

| Column   | Type       | Options                        |
| ---------| ---------- | ------------------------------ |
| text     | text       | null: false, foreign_key: true |
| user     | references | 
| prototype| references |

### Association

- belongs_to :user
- belongs_to :post






## like table
| Column   | Type       | Options                        |
| ---------| ---------- | ------------------------------ |
| user     | references | 
| post     | references |

### Association

- belongs_to :user
- belongs_to :post

