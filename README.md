# **概要**
スクレイピングで取得したデータを成型し、SQLの登録用CSVの作成

使用ソフト

・Python　

・EXCEL MICROSOFT365　

・DB Browser for SQLite 3.32.2

# python version

・Python	3.8.13

・numpy	1.18.5

・pandas	1.5.1

・matplotlib	3.5.1

・beautifulsoup4	4.11.1

・urllib3		1.26.12 

・keras	2.4.3 

・tensorflow	2.3.0

# 実行ファイル 1
 
**01_complete_pitcher_league.ipynb**

パワプロのデータをwebよりスクレイピングでデータを取得する。(複数年分取得可能)

セ・リーグかパ・リーグを選択し、選択したリーグの6チーム分のデータを取得する。

投手、野手で項目が変わるため、個別に作成する。

ステータスをまず取得する。

背番号が別ページにあるため、「名前と背番号」を別途取得。

pandasで[ ステータス ] のDFと [ 名前、背番号 ] のDFを名前をキーにして結合。

チームごとに結合後、一括処理でリーグの投手データに処理してcsvに保存する。

# 実行ファイル 2

**02_complete_fileder_league.ipynb**

投手データと同様にデータを取得する。

投手データと同様にpandasで[ ステータス ] のDFと [ 名前、背番号 ] のDFを名前をキーにして結合。

チームごとに結合後、一括処理でリーグの野手データに処理してcsvに保存する。




