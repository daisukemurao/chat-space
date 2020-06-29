## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index: true|
|email|string|null: false,unique: true|
|password|string|null: false|

### Asociation
has_many :groups_users
has_many :groups
has_many :massages

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|groups_name|string|null: false, unique: true|

### Asociation
has_many :groups_users
has_many :users
has_many :massages

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|