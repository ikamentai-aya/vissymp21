# 議論

この章では３章で定義した提案手法の果たすべき小目標を達成できているのか議論を行う。小目標は以下の通りであった。
-（P1) 小説のどの部分を読んでいても、人物相関図によってネタバレを起こさないこと
-（P2) 小説内の繊細な人間関係を記載し、ユーザーがそれを確認できること
-（P3) 入力した情報をもとに人物相関図を自動でレイアウトしてくれること

## （P1) 小説のどの部分を読んでいても、人物相関図によってネタバレを起こさないこと

本研究ではこの小目標を達成するために**読書の進度によって変化する動的人物相関図**を提案した。提案手法では登場人物や人物間の関係性は小説のページが進むにつれて登場しその後持続して存在するものとして扱う。そして現在表示しているページまでに出てきた登場人物と関係性を元に**人物相関図**と**人物相関表**という２種類の可視化を行う。これによりユーザーは表示するページ数の範囲を指定して人物相関図を表示することができ、ネタバレを受けずに書籍の内容を整理することができる。一方課題点は2点ある。1点目はシステムの誤操作によって意図せずまだ読んでいない部分の情報を取得してしまう可能性があることである。今回人物相関図表示する内容は「現在表示しているページまでに出てきた情報」を表示しているため、スクロールバーの操作を間違えてまだ読んでいない部分を選択するとその時点までの登場人物と関係を人物相関図に表示してしまう。今後の課題としては意図しない表示が行われないための仕組み作りがあげられる。2点目は人物相関図に表示された登場人物からネタバレを起こす可能性がある点である。現在一人の登場人物に対し名前が一つ対応しており、それは何度でも修正することができる。加えて小説内の関係情報は他者と共有されているため、先に読んだ人が自分の読んだ内容に合わせて登場人物の名前を修正している場合、登場人物の真の名前が人物相関図に表示される可能性がある。登場人物の名前がわざと序盤において隠されていたり展開に大きく影響している場合があるため、登場人物の真の名前を知ることでネタバレにつながる可能性がある。そのため今後の課題として


## （P2) 小説内の繊細な人間関係を記載し、ユーザーがそれを確認できること

この小目標を達成するためにシステムの要件として****、****


## （P3) 入力した情報をもとに人物相関図を自動でレイアウトしてくれること



