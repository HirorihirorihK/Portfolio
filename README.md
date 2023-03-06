# **目的**

データ収集からデータ整形、加工、分析、予測を行うこと

職業訓練で学んだことを一連の流れで行うこと

# **概要**

スクレイピングで取得したデータを整形し、データベース登録用CSVの作成

及び、作成したCSVで機械学習を用いた分析

# 使用ソフト

・Anaconda Navigator 2.3.1 (anaconda3)

・Visual Studio Code 1.65.0 

・Python　

・EXCEL MICROSOFT365　

・DB Browser for SQLite 3.32.2

# Python version

・Python	3.8.13　　　

・numpy	1.18.5

・pandas	1.5.1

・matplotlib	3.5.1

・beautifulsoup4	4.11.1

・urllib3	1.26.12

・keras	2.4.3 

・tensorflow	2.3.0

・openpyxl 3.0.10

・xlrd 2.0.1

# 実行する際に

ファイルを実行する際は、フォルダを作成しipynbファイル4つと2023_baseball.xlsxを同じフォルダに入れて、実行してください

実行した結果のファイルは「取得済み参考データ一覧」に入っています

# 実行ファイル 1
 
**01_Complete_pitcher_league_2023.ipynb**

パワプロのデータをwebよりスクレイピングでデータを取得する。(複数年分取得可能)

セ・リーグかパ・リーグを選択し、選択したリーグの6チーム分のデータを取得する

投手、野手で項目が変わるため、個別に作成する

ステータスをまず取得する。背番号が別ページにあるため、「名前と背番号」を別途取得

pandasで[ ステータス ] のデータフレームと [ 名前、背番号 ] のデータフレームを名前をキーにして結合

チームごとに結合後、一括処理でリーグの投手データに処理してcsvに保存する

# 実行ファイル 2

**02_complete_fileder_league.ipynb**

野手データを取得する。

投手データと同様にpandasで[ ステータス ] のDFと [ 名前、背番号 ] のDFを名前をキーにして結合

チームごとに結合後、一括処理でリーグの野手データに処理してcsvに保存する

# 実行ファイル 3

**03_LinearRegression_2023.ipynb**

1.実行ファイル1,2で作成したcsvを読み込み、一つのデータに統合

2.チームのステータスを各年度ごとの平均値にして、データフレーム化

(2011 2012 2013 2014 2016 2018 2020 2022　※ナンバリングタイトルの年度)

3.目的変数、説明変数に分け、線形回帰で勝率の予測モデルを作成(2022以外を使用)

決定係数: 約0.618

4.予測モデルで2022のデータを用いて、勝率を予測

予測値　1位: 中日:62.19%　2位: 巨人: 59.44%　3位: DeNA:53.17%　4位: 広島:51.70%　5位: ヤクルト:48.15%　6位: 阪神:47.15%

# 実行ファイル 4

**04_NeuralNetwork_2023.ipynb**

1, 2.上記実行ファイル3の1,2を同様に行う

3.目的変数、説明変数に分け、さらにトレーニングデータとテストデータに分ける

4.ニューラルネットワークで予測モデルを作成　損失関数MSE(平均二乗法誤差)

5.予測モデルで2022のデータを用いて、勝率を予測

予測値　1位: 巨人:48.55%　2位: 中日:48.15%　3位: DeNA:47.04%　4位: 広島:44.57%　5位: 阪神:42.95%　6位: ヤクルト:41.82%

# 実行ファイル 5

**05_csv_converter.ipynb**

Pythonで出力したcsvファイルの文字コードがutf-8のため、excelで開く際クエリ等を適用せずにエクセルで開けるように作成

また、複数ファイル(単ページ)のものを、1つのファイルにまとめられるものも作成

出力する際に、オプションとしてヘッダー情報のオンオフを追加


