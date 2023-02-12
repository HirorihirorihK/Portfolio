# **概要**
スクレイピングで取得したデータから成型を行い、SQLの登録用CSVの作成

使用ソフト

・Python　

・EXCEL MICROSOFT365　

・DB Browser for SQLite 3.32.2

# version

・Python	3.8.13

・numpy	1.18.5

・pandas	1.5.1

・matplotlib	3.5.1

・beautifulsoup4	4.11.1

・urllib3		1.26.12 

・keras	2.4.3 

・tensorflow	2.3.0

# 実行ファイル
 
**0212_pithcer_select_year.ipynb**

パワプロのデータをwebよりスクレイピングでデータを取得する。

セ・リーグかパ・リーグを選択し、選択したリーグの6チーム分のデータを取得する。

投手、野手で項目が変わるため、投手から先に作成する。

ステータスをまず取得する。

背番号が別ページにあるため、「名前と背番号」を別途取得。

投手、野手共に取得され、再利用のためcsvで保存。

pandasで[ ステータス ] のDFと [ 名前、背番号 ] のDFを名前をキーにして結合。

チームごとに結合後、一括処理でリーグの投手データに処理してcsvに保存する。







