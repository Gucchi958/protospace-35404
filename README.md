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

#テーブル設計

##　users　テーブル
| Column     | Type   | Options      |
| ---------- | ------ | ------------ |
| email      | String | null: false  |
| password   | String | null: false  |
| name       | String | null: false  |
| profile    | Text   | null: false  |
| occupation | Text   | null: false  |
| position   | Text   | null: false  |

### Association
- has_many :prototypes
- has_many :comments

## prototypes テーブル
| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| title      | String     | null: false                    |
| catch_copy | Text       | null: false                    |
| concept    | Text       | null: false                    |
| user       | references | null: false, foreign_key: true |

### Association
- belong_to :user
- has_many  :comments

## comments テーブル
| Column    | Type       | Option                          |
| --------- | ---------- | ------------------------------- |
| text      | Text       | null: false                     |
| user      | references | null: false, foreign_keys: true |
| prototype | references | null: false, foreign_keys: true |

### Association
- belong_to :user
- belong_to :prototype

