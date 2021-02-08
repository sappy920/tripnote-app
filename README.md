# README

## Usersテーブル

|Column                |   Type     |Options                  |
|----------------------|------------|-------------------------|
| name                 | string     |null: false              |
| email                | string     |null: false, unique: true|
| encrypted_password   | string     |null: false              |
| birthday             | date       |null: false              |

### Association
- has_many :photos
- has_many :comments
- has_one :profile


## Photosテーブル
|Column                |    Type         |Options                         |
|----------------------|-----------------|--------------------------------|
| instruction          | text            |null: false                     |
| category_id          | integer         |null: false                     |
| country_id           | integer         |null: false                     | 
| user                 | references      |null: false, foreign_key: true  |

### Association
 - belongs_to :user
 - has_many :comments


 ## Commentsテーブル
|Column                |    Type         |Options                         |
|----------------------|-----------------|--------------------------------|
| text                 | text            |null: false                     |
| user                 | references      |null: false, foreign_key: true  |
| photo                | references      |null: false, foreign_ket: true  |

### Association
- belongs_to user
- belongs_to photo




 ## Profilesテーブル
|Column                |    Type         |Options                         |
|----------------------|-----------------|--------------------------------|
| instruction          | text            |null: false                     |
| travel_history       | text            |null: false                     |
| user                 | references      |null: false, foreign_key: true  |

### Association
- belongs_to :usr