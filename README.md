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
①チームとして工夫を行った点  
　初めにデータベース作業担当を1人決め、それ以外のメンバーでフロント実装に取り掛かった為、タスク進行が非常に円滑に進みました。  
　その分、メンバー全員でバックエンドに取り組むことができたので、各々が不安点、不明点を解消しながら作業を進めることができました。  
②個人として工夫を行った点  
　チーム開発初日から、体調不良に見舞われてしまった為、DB設計に携われず、内容把握に遅れを取ってしまいましたが、その分「自分にできることは何か？」を考えました。  
　結果、”チーム開発”ということにフォーカスして、チームでの作業の進め方や、取り組み方を見直して、チームに提案し、改善に努めました。  
　最終的にはメンバー各々がコンフリクトをいかに避けるかを改めて考え直す機会を設けられたのはよかったと思います。  
 
## 苦労したポイント
①NewアクションとEditアクションの記述の相違点   
　今まで作成してきた簡易的なアプリですと、NewアクションとEditアクションの違いがそこまで無い様に思っていましたが、  
　今回の様な１つの項目に複数投稿する（画像など）時と、更新をする時とでは全く考え方や記述が異なることに最初は困惑しました。  
　しかし苦労した分、実装まで持ってこれたのは自信につながりましたし、今後のタスク配分の時の判断材料として良い経験になりました。  
  
②”チーム開発をする”という意味の理解、共有  
　今までは個人開発として、各々好きな様にブランチを切り、作業に取り掛かり、マージをして…という繰り返しでしたので、  
　チーム開発を開始した当初は、高確率でコンフリクトを起こしてしまっていました。  
　「スクールの段階でチーム開発を経験する意味」とは何かを考えた結果、  
　「企業に就職した後に、仕事としていち早くチームとしての動きに馴染める様にする為」であると私は思いました。  
　それをいかにチームメンバーに共有し、理解してもらうかを課題に、マインドマップツールを用い図化し、  
　自分の言葉で説明を試みたところ、メンバーには理解してもらい、その後の開発でのコンフリクトは激減しました。  
　この経験を経て、自ら改善を試みる時には、それがいかに正論であろうとも、  
　相手に理解をもらう為に工夫が必要であるということが分かり、この取り組みは今後プロジェクトに参画した際にも有効であると感じました。  
  
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
