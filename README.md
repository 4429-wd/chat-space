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


# Chat-Space DB設計
## usersテーブル
|colum|Type|Options|
|-----|----|-------|
|email|string|null: false|
|password|string|null: false|
|nickname|string|null: false|
### Association
-has_many :messages
-has_many :groups, through: :group

## groupsテーブル
|colum|Type|Options|
|-----|----|-------|
|group_name|string|null: false|
|users_name|string|null: false|
### Association
-has_many :users
-has_many :messages

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

## messageテーブル
|Column|Type|Options|
|------|----|-------|
|text|text||
|image|text||
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user