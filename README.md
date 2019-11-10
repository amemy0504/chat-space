# README
## usersテーブル
|column|Type|Options|
|------|----|-------|
|name|string|null: false, index: true|
|email|string|null: false|
|password|string|null: false|
### Association
- has_many :messages
- has_many :users_groups
- has_many :groups, through:  :users_gruops

## groupsテーブル
|column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many :messages
- has_many :users_groups
- has_many :users, through:  :users_groups

## users_groupsテーブル
|column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integr|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

## messagesテーブル
|column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

