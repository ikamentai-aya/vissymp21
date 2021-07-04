# 可視化システム（一旦書きおわり）
4.1にて設定した要件をもとにシステムを設計した。この節では要件に沿ってシステムの説明を行う。

## (N1)システムの上で読書ができること

様々な電子書籍リーダーを参考にし、読書に必要な機能を最低限実装した。読書画面には、小説の選択機能、本文の表示、しおりなどの機能が実装されている。**小説を選択**ボタンを押すと新しく小説を青空文庫のサイトからダウンロードするか、既にダウンロードした小説から選ぶのか選択することができる。小説をダウンロードする時は、青空文庫の作品の図書カードページのリンクを貼り付ける。貼り付けると、青空文庫のデータを表示しやすい形へ成形しシステム上に保存する。ダウンロード済みの作品を選ぶ際は、作品の一覧から自分の読みたい作品を選択する。選択された小説の本文はシステムの左下に表示され、 最初に読むときは１ページ目が、2回目以降に読む場合は前回最後に読んだページが表示される。元々の青空文庫で公開しているデータには区切りがないが、そのままシステム上に表示すると読んだ部分の把握が難しくなるので、一定文字数で区切りページとして管理している。
システムの上部には読書を進めるためのツールが位置している。左端のスライダーではつまみを動かして、見たいページを選択しそのページに飛ぶことができる。「◁」を押すと前のページへ、「▷」を押すと次のページへとめくることができる。次の「しおり」と書かれたボタンを押すと現在表示しているページをしおりづけできる。最後に「しおりに飛ぶ」ボタンを押すと、以前に追加したしおりのページを選択しそのページに飛ぶことができる。

## (N2)情報の追加方法
この節では読んだ小説内の情報をシステムに追加する方法を紹介する。このシステムで入力できる情報はで議論した通り、登場人物と関係性の二つである。システム上で入力された情報はシステムを閉じても保存され続ける。情報追加は手動と自動の二通りで行えるので順番に紹介する。

### 自動抽出
自動抽出は**自動情報抽出**ボタンを押すことで、小説内の登場人物と人間関係の候補を自動で全て抽出することができる。抽出された情報は自動で保存され、その情報はシステム内で確認することができる。

### 手動抽出
登場人物の追加方法は主に二つである。一つ目の方法は完全に手作業で追加する方法である。1 番上の**情報追加**ボタンを押すと、人物を追加するか、関係を追加するか選ぶことができる。人物の追加を選ぶと、情報入力画面が出る。テキストボックスに追加したい登場人物を入力し、**以上の人物を追加**ボタンを押すと、入力した人物が登場人物のリストに追加される。二つ目の方法は計算機を用いて登場人物の候補を提案し、その中から人物を選んでもらう方法である。 **登場人物の候補を抽出**ボタンを押すと、現在表示している文章内の登場人物らしい単語を抽出して表示する。候補のうちチェックを付けたものは文中での色が変化するので、その単語が本当に登場人物を指すのか確認できる。最後に登場人物として追加したいものだけチェックをつけて、**追加**ボタンを押すとまとめて登場人物に追加される。

次に関係性の追加方法について紹介する。システムの上部の**情報追加**ボタンを押し、**関係性追加**を選択すると関係性の入力フォームが出現する。そこでその関係が**誰から**、**誰への**、**どんな関係**で**どのくらい好意的なのか**を入力する。好感度は５段階評価で高い値ほど好感度が高いことを示す。以上の情報を入力し終わったら**追加**ボタンを押すことで入力した関係性はシステムに保存される。

## (N3) 情報を後から編集できること

この節では既に追加した情報を修正する方法について紹介する。情報編集は**情報編集画面**を開くことで行うことができる。情報編集画面は**登場人物編集表**と**登場人物の出現度のヒートマップ**と**関係編集画面**の3つから成り立つ。登場人物の情報を編集する場合は表において変更したい部分をダブルクリックし直接書き換えることができる。しかし書き換えただけではシステムに保存された情報は変わらないので右にある**変更を保存**ボタンを押す必要がある。加えて登場人物の左横にチェックをつけると登場人物が選択され、選択された人物はヒートマップ上に表示される。右の**消去**ボタンを押すとチェック付きの人物をまとめて消去することができる。これは関係編集画面も同様に操作することができる。
ヒートマップにおいて縦軸は登場人物、横軸はページ数を表している。各セルはそのページにおいて登場人物の単語が何回出てきたかによって色分けされており、濃い色であるほど登場回数が多い。カーソルを各セル上におくと、そのセルが「誰のどのページでの出現回数」を表していて、正確な出現回数を確認することができる。加えて各セルをクリックするとそのセルの表すページへ飛ぶことができる。


## (N4) 小説の進行度に合わせて関係図を表示すること

最後に関係図を表示する機能について紹介する。本研究では登場人物と関係を表すために**人物相関図**と**人物相関表**という２種類の表示を行う。

### 人物相関図
人物相関図はノードリンクである。人物相関図は上の**可視化を選択**から**人物相関図**を選択することで表示できる 。人物相関図には現在のページまでに出てきた登場人物と関係の情報が表示される。各ノードは登場人物を表し、各リンクは1番直近の関係性を表している。各ノードの大きさはその人物の持つ関係性の多さを表し、大きいほど小説において重要な人物である。ノード上でクリックをするとそのノードに繋がったリンクのみが強調され、関係する人物を一眼で確認できる。加えて各リンクはその関係の持つ好感度の値によって色付けされている。各リンクの上をホバーすると関係についての正確な情報を得ることができる。人物相関図は登場人物が少ない場合に一目で重要な人物や関係性を確認することができ、多くのユーザーに馴染み深い表示手法を採用しているため内容を理解しやすいという利点がある。

### 人物相関表
次に人物相関表の紹介を行う。人物相関表はシステムの上部の**可視化を選択**から**人物相関表**を選ぶことで表示できる。人物相関表では現在のページまでに出てきた人物の名前が縦軸と横軸に並ぶ。各セルは縦軸の人物から横軸の人物への直近の関係を表しており、その関係の好感度によって色分けされている。またセル上をホバーすることでその関係の詳細を確認でき、クリックすることで過去の関係の一覧表を見ることができる。人物相関表の隣には表示する範囲を制限するためのボタンが位置する。これらのボタンでは、**小説のどのページの関係を表示するのか**、**どの人物に注目した人物相関表を表示するのか**、**人物相関表にどの人物を表示するのか**の３つを調整することができる。 人物相関表の機能は以上の通りである。人物相関表の長所は登場人物の多い長い小説に対しても、機能を使えばある程度対応することができることである。
このように人物相関図と人物相関表では長所が異なっているため、人物の数や知りたい情報によってビューを使い分けることを想定している。

以上のようにまた各システム要件に必要な機能を実装することができた。









