## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false,unique: true|
|pssword|string|null: false|
|password_confirmation|string|null :false|

### Association
has_many :comments  
has_many :posts  
has_many :likes  

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|comment|string|null: false|
|post_id|references|foreign_key: true|
|user_id|references|foreign_key: true|

### Association
belongs_to :user  
belongs_to :posts  

## postsテーブル
|Column|Type|Options|
|------|----|-------|
|caption|string|null: false|
|user_id|references|foreign_key: true|

### Association
belongs_to :user  

## likesテーブル
|Column|Type|Options|
|------|----|-------|
|post_id|references|foreign_key: true|
|user_id|references|foreign_key: true|

### Association
belongs_to :user  
belongs_to :posts  

## photosテーブル
|Column|Type|Options|
|------|----|-------|
|image|string|null :false|
|post_id|references|foreign_key: true|

### Association
belongs_to :posts  