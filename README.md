DB設計

## usersテーブル
|columu|Type|Options|
|------|----|-------|
|name|string|index: true, null: false. unigue: true

### Association
- has_many :groups, through: :members
- has_many :messages
- has_many :members

## groupsテーブル
|columu|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true

### Association
- has_many :users, through: :members
- has_many :messages
- has_many :members

## messages
|columu|Type|Options|
|------|----|-------|
|body|string|
|image|string|
|user|references|null: false, foreign_key; true
|group|references|null: faise, foreign_key: true

### Assoviation
- belongs_to :group
- belongs_to :user

## membersテーブル
|columu|Type|Options|
|------|----|-------|
|user|references|null: faise, foreign_key: true
|group|references|null: false, foreign_key: true

### Association
- belongs_to :group
- belongs_to :user


