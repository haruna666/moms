# アプリケーション名
”WeGrow for mom”

# ”ママのマインドチェンジをするオンラインスクールです。ママが変わることで、これからの子供達の気持ちを認め作り出し、やがて全く新しい日本を作り出す20年先を見据えた改革です”
次世代の子供たちは、これまでの子供たちとは違う世界を生きる。
ならば、子供に一番影響のあるママ自体が変わり、先の世界を見つめながら子育てをする。
そのためのママオンラインスクールを作成しました。
ママの意識を変え、今を生きる私たち、そしてこれからを生きる子供たちへの大きな影響力を考える、学びとコミュニティが合わさった日本をレベルアップさせるためのスクールです。

# 開発環境
Ruby2.6.6/Ruby on Rails6.0.3.7/Mysql/git hub/Sequel Plo

## 要件定義

| 機能              | 目的                     | 詳細                 | ストーリー           | 見積もり時間   |
| ---------------- | ------------------------ | ----------------------------| ----------------------- | ------------ |
| DB設計            | アプリ作成の全体像を洗い出す |              |               | 6            |
| ユーザー管理機能    | deviseを用いたユーザー管理機能| Topページにログイン、新規登録ボタン、ログインしている場合はログアウトボタンを表示 |    | 6 |
| 動画一覧表示機能    | 動画一覧をログインユーザーが閲覧できる | 動画イメージ写真、動画名、動画説明、料金を表示 | レッスン動画の一覧を表示 | 一覧から動画を選択すると動画詳細ページへ遷移する  | 6 |
| 動画新規登録機能   | lesson動画を主催者がupするためのページ | 主催者のみ投稿可能、動画イメージ写真、動画名、動画説明、料金を登録 | 主催者のみこのページへアクセスでき、投稿できる  |  7 |
| 動画詳細表示機能  | １つの動画の詳細を一覧で選択し動画詳細ページへ遷移する |動画イメージ写真、動画名、動画詳細、料金、購入ボタンを設置 | ログインユーザーのみ購入できる | 5 |
| 動画編集機能    | すでにupしている動画の詳細などを主催者が編集できるページへ遷移、詳細画面から遷移できるように実装 |主催者のみ編集可能、動画名、動画イメージ写真、詳細、料金を編集できる | 主催者のみこのページにアクセスできる| 5 |
| 動画購入機能     | 動画詳細画面から選択した動画をログインユーザーが購入できる | 動画イメージ、動画名、料金を表示、クレジットカード決済を用いた支払い機能を実装 | ログインユーザーのみ利用可能 | 5 |
| レビュー評価機能 | 購入したユーザーが評価し、このページを全ての人が閲覧できる、主催者はレビューに対して返信できる |評価をもらい、購入者の不安を解消   | 主催者はフィードバックをもらい、更に品質の向上を目指す  | 6 |



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

<!-- - has_many :chats -->
<!-- - has_many :yogas -->
<!-- - has_many :lesson_movies -->
- has_many :items
- has_many :orders


<!-- # chats テーブル

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
- belongs_to :user -->


<!-- # lesson_movies テーブル

| Colum          | Type       | Option                          |
| -------------- | ---------- | ------------------------------- |
| user           | references | null: false, foreign_key: true  |
| comment        | string     | null: false                     |

# Association

- belongs_to :user -->


# items テーブル

| Colum         | Type        | Option                           |
| ------------- | ----------- | -------------------------------- |
| name          | string      | null: false                      |
| price         | integer     | null: false                      |
| detail        | string      | null: false                      |
| user          | reference   | null: false, foreign_key: true   |
| comment       | string      |                                  |

# Association

- belongs_to :user
- has_many :order


# Orders テーブル

| Colum         | Type        | Option                          |
| ------------- | ------------| ------------------------------- |
| user          | references  | null: false, foreign_key: true  |
| item          | references  | null: false, foreign_key: true  |
| 

# Association

- belongs_to :user
- belongs_to :item

# images テーブル

| Colum       | Type       | Option              |
| ----------- | ---------- | ------------------- |
| image       |            |                     |
| item        | references | foreign_key: true   |

# Association

-belongs_to :item