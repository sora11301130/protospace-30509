users テーブル
|  Column     |  Type      |  Options         |
| ----------- | -----------| -----------------|
| email       | string     | null:false       |
| password    | string     | null:false       |
| name        | string     | null:false       |
| profile     | text       | null:false       |
| occupation  | text       | null:false       |
| position    | text       | null:false       |

### Association

- has_many :prototype
- has_many :comments

prototype テーブル
|  Column     |  Type      |  Options                    |
| ----------- | -----------| --------------------------- |
| title       | string     | not:null                    |
| catch_copy  | text       | not:null                    |
| concept     | text       | not:null                    |
| user        | reference  | not:null, foreign_key:true  |

## Association

- belongs_to :users
- belongs_to :comments


comments テーブル
|  Column     |  Type      |  Options                    |
| ----------- | -----------| --------------------------- |
| text        | text       | not:null                    |
| user        | reference  | not:null, foreign_key:true  |
| prototype   | reference  | not:null, foreign_key:true  |

## Association
- belongs_to :users
- belongs_to :prototype
