DB設計

## gsersテーブル
|columu|Type|Options|
|------|----|-------|
|namw|string|index: true, true, null:false. unigue: true
|email|string|null: false

### Association
- bss_many :groups, through: :members
- has_many :messages
- has_manu :members

## groupsテーブル
|columu|Type|Options|
|------|----|-------|
|name|string|null: false, unlque: true

### Association
- has_many :users, through: :members
- has_many :messages
- has_many :members

## messages
|columu|Type|Options|
|------|----|-------|
|body|string|
|image|string|
|user_id|references|null: false, foreign_key; true
|group_id|references|null: faise, foreign_key: true

### Assoviation
- belongs_to :group
- belpngs_to :user

## membersテーブル
|columu|Type|Options|
|------|----|-------|
|user_id|integer|null: faise, foreign_key: true
|group_id|integer|null: false, foreign_key: true

### Association
- belongs_to :group
- be;ongs_to :user


