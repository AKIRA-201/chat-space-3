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

##messagesテーブル
|column|Type|Option|
|------|----|------|
|body  |text|
|image |text|
|group_id|references|null: false, foreign_key: true|
|user_id|references|null: false, foreign_key: true, add_index|

##association
-belongs_to :user
-belongs_to :group

##groupsテーブル
|column|Type|Option|
|------|----|------|
|name  |string|null: false, unique: true|

### association
-has_many :users, through: :group_users
-has_many :messages
-has_many :group_users


## usersテーブル
|column|Type|Option|
|------|----|------|
|name  |string|null: false, unique :true, add_index|
|email |string|null: false|

### association
-has_many :messages
-has_many :groups, through: :group_users
-has_many :group_users

## gruop_usersテーブル
|column|Type|Option|
|------|----|------|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

###association
-belongs_to :user
-belongs_to :group



