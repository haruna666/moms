# ”ママのマインドチェンジは、これからの子供達の気持ちを認め作り出すこと、やがて全く新しい日本を作り出すオンラインスクール”
次世代の子供たちは、これまでの子供たちとは違う世界を生きる。
ならば、子供に一番影響のあるママ自体が変わり、先の世界を見つめながら子育てをする。
そのためのママオンラインスクールを作成しました。
ママの意識を変え、今を生きる私たち、そしてこれからを生きる子供たちへの大きな影響力を考える、学びとコミュニティが合わさった日本をレベルアップさせるためのスクールです。

# 開発環境
Ruby2.6.6/Ruby on Rails6.0.3.7/Mysql/git hub/Sequel Plo

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
