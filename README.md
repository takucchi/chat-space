## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|index: true, null: false, unique: true|

### Association
- has_many :messages
- has_many :members
- has_many :groups, through: members


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :messages
- has_many :members
- has_many :users, though: members


## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|text|string|       |
|image|string|      |
|user|references|null:false,foreign_key:true|
|group|references|null:false,foreign_key:true|

### Association
- belongs_to: user
- belongs_to: group
