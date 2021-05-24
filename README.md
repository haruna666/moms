# Users テーブル

| Colum             | Type    | Options      |
|------------------ |-------- |------------- |
| nickname          | string  | null: false  |
| encrypted_password| string  | null: false  |
| email             | string  | null: false  |
| last_name         | string  | null: false  |
| first_name        | string  | null: false  |
| furigana_last     | string  | null: false  |
| furigana_first    | string  | null: false  |
| date_of_birth     | date    | null: false  |

# Association

- has_many :chats
- has_many :yogas
- has_many :lesson_movies
- has_many :items
- has_many :oders


# chats テーブル

| Colum           | Type       | Option                          |
|---------------- | ---------- | ------------------------------- |
| user            | references | null: false, foreign_key: true  |
| comment         | string     | null: false                     |

# Association

- belongs_to :user


# yogas テーブル

| Colum          | Type       | Option                          |
| -------------- | ---------- | ------------------------------- |
| user           | references | null: false, foreign_key: true  |
| comment        | string     | null: false                     |

# Association
- belongs_to :user


# lesson_movies テーブル

| Colum          | Type       | Option                          |
| -------------- | ---------- | ------------------------------- |
| user           | references | null: false, foreign_key: true  |
| comment        | string     | null: false                     |

# Association

- belongs_to :user


# items テーブル

| Colum         | Type        | Option                           |
| ------------- | ----------- | -------------------------------- |
| name          | string      | null: false                      |
| price         | integer     | null: false                      |
| detail        | string      | null: false                      |
| user          | reference   |  null: false, foreign_key: true  |

# Association

- belongs_to :user
- belongs_to :order


# Orders テーブル

| Colum         | Type        | Option                          |
| ------------- | ------------| ------------------------------- |
| user          | references  | null: false, foreign_key: true  |
| item          | references  | null: false, foreign_key: true  |
| 

# Association

- belongs_to :user
- has_many :items
