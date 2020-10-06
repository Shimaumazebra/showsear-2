## users テーブル

| Column          | Type    | Options     |
| --------------- | ------  | ----------- |
| name            | string  | null: false |
| email           | string  | null: false |
| password        | string  | null: false |
| last_name       | string  | null: false |
| first_name      | string  | null: false |
| last_name_kana  | string  | null: false |
| first_name_kana | string  | null: false |
| date_of_birth   | date    | null: false |


### Association

- has_many :items
- has_many :comments

## items テーブル

| Column                | Type       | Options                            |
| --------------------- | ---------- | ---------------------------------- |
| user                  | references | null: false, foreign_key: true     |
| name                  | string     | null: false                        |
| description           | text       | null: false                        |
| gender_id             | integer    | null: false                        |
| category_id           | integer    | null: false                        |
| brand_id              | integer    | null: false                        |
| prefecture_id         | integer    | null: false                        |
| aging_id              | integer    | null: false                        |
| price 　　　           | integer    | null: false                        |

### Association

- belongs_to : users
- has_one    : comments

## comments テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| user    | references | null: false, foreign_key: true |
| item    | references | null: false, foreign_key: true |

### Association

- belongs_to : users
- belongs_to : items

