# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version
gem install rails --version="5.0.7.2"

* System dependencies

* Configuration

* Database creation

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|
### Association
- has_many :comments
- has_many :groups,  through:  :groups_users
- has_many :groups_users
## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many :comments
- has_many  :users,  through:  :groups_users
- has_many :groups_users

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text||
|image|text||
|group_id|string|null: false|
|user_id|string|null: false|
### Association
- belongs_to :group
- belongs_to :user


## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
