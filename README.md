# FURIMA

## 概要
 テックキャンプの最終課題にて作成したフリーマーケットアプリケーションです。  
 こちらには自信で実装した箇所や開発を通じて学んだことを共有したいと思います。

## 本番環境

http://18.180.99.238/

## 実装箇所
 - 商品詳細ページ（フロント、バック）  
 　　■ページ上部にカテゴリーの階層を実装  
 　　■詳細内容のテーブル表示  
  
 - カテゴリー一覧とカテゴリー別商品一覧、ページ内遷移（フロント、バック）  
 　　■カテゴリーの項目を作成  
 　　■一覧ページにページ内遷移を実装  
 　　■カテゴリー毎の商品一覧  
  
 - 商品出品と商品内容編集ページのカテゴリー多階層選択（バック）  
 　　■カテゴリーの多階層表示、選択  
  
## DEMO
 - 商品詳細ページ（フロント、バック）  
   http://18.180.99.238/products/5  
    ○if分岐を用いて、カテゴリーの階層表示を実装  
    ○tableタグを用いて詳細内容を見やすく整理  

![2eaf12f8f14f2d29b06f5f9ec08e2658](https://user-images.githubusercontent.com/59810246/77713656-42c6b200-701a-11ea-8165-3a8b1fa89623.gif)
  
 - カテゴリー一覧とカテゴリー別商品一覧、ページ内遷移（フロント、バック）  
 　http://18.180.99.238/categories  
    ○gem ancestoryとseedファイルを用いて、カテゴリーの項目を一括作成  
    ○anchorを用いたページ内遷移を実装  
    ○カテゴリーに含まれる商品を呼び出し表示させる  
  
![8e19ef4e8073ebe4806c1a634936d0e2](https://user-images.githubusercontent.com/59810246/77713710-71dd2380-701a-11ea-94cf-ed89be3a7c4b.gif)  
  
![e519be759d710d4b91eac3b7d8812997](https://user-images.githubusercontent.com/59810246/77714368-32afd200-701c-11ea-8735-f825adcd88af.gif)  
  
![6a7b3291fb02e6f1685ae392deba2f82](https://user-images.githubusercontent.com/59810246/77714580-afdb4700-701c-11ea-8847-e832b346daa7.gif)  
  
 - 商品出品と商品内容編集ページのカテゴリー多階層選択（バック）  
 　http://18.180.99.238/products/new  
    ○gem ancestoryを用いたカテゴリーの親子孫関係を紐付け  
    ○JavaScriptを用いたプルダウン式の選択肢を実装  
  
![dc2c0587306af9fed38b486ad99683d9](https://user-images.githubusercontent.com/59810246/77715618-63ddd180-701f-11ea-9a78-8f25237c2617.gif)  


## 工夫したポイント



## 使用技術

HTML5  
SCSS3  
jQuery  
Ruby2.5.1  
Rails5.2.4.1  
MySQL  
AWS

## 課題や今後実装したい機能




# DB設計

### usersテーブル
|Column|Type|Options|
|------|----|-------|
| nickname           | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |
| user_image         | string ||
| introduction       | text   ||
| family_name        | string | null: false |
| first_name         | string | null: false |
| family_name_kana   | string | null: false |
| first_name_kana    | string | null: false |
| birth_day          | date   | null: false |

#### Association
- has_many   :products       dependent: :destroy
- belongs_to :destination    dependent: :destroy
- belongs_to :card           dependent: :destroy


### destinationテーブル
|Column|Type|Options|
|------|----|-------|
| user_id          | integer | null: false, foreign_key: true|
| family_name      | string  | null: false|
| first_name       | string  | null: false|
| family_name_kana | string  | null: false|
| first_name_kane  | string  | null: false|
| post_code        | string  | null: false|
| prefecture       | string  | null: false|
| city             | string  | null: false|
| address          | string  | null: false|
| building_name    | string  ||
| phone_number     | string  ||

#### Association
- belongs_to :user


### cardテーブル
|Column|Type|Options|
|------|----|-------|
| user_id     | integer | null: false, foreign_key: true |
| customer_id | string  | null: false |
| card_id     | string  | null: false |

#### Association
- belongs_to :user


### categoryテーブル
|Column|Type|Options|
|------|----|-------|
| name     | string | null: false |
| ancestry | string ||

#### Association
- has_many :products


### productテーブル

|Column|Type|Options|
|------|----|-------|
| name          | string  | null: false |
| price         | string  | null: false |
| description   | string  | null: false |
| status        | string  | null: false |
| size          | string  | null: false |
| shipping_cost | string  | null: false |
| shipping_days | string  | null: false |
| prefecture_id | string  | null: false |
| judgment      | string  ||
| category_id   | integer | null: false, foreign_key: true |
| brand_id      | integer | null: false, foreign_key: true |
| shipping_id   | integer | null: false, foreign_key: true |
| user_id       | integer | null: false, foreign_key: true |

#### Association
- belongs_to :user       dependent: :destroy
- belongs_to :category   dependent: :destroy
- belongs_to :brand      dependent: :destroy
- has_many   :images     dependent: :destroy

- belongs_to_active_hash :prefecture


### imageテーブル
|Column|Type|Options|
|------|----|-------|
| image      | string  | null: false |
| product_id | integer | null: false, foreign_key: true |

#### Association
- belongs_to :product


### brandテーブル
|Column|Type|Options|
|------|----|-------|
| name | string | index: true |

#### Association
- has_many :products
