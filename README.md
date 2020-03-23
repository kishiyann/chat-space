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
### Association
- has_many :groups
- has_many :comments

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|image|text||
|text|text||
### Association
- has_many :users
- has_many :comments
- has_many :groups_users
- has_many  :comments,  through:  :groups_users

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
### Association
- belongs_to :group
- belongs_to :user
- has_many :groups_users
- has_many  :groups,  through:  :groups_users


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
