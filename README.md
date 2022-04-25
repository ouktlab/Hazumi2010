# Hazumi2010
Osaka University Multimodal Dialogue Corpus (Hazumi2010)

Hazumi2010では以下のファイル群を公開している（もしくは公開予定）．
```
1. ビデオデータ（未）
2. 閲覧用ELANファイル
3. 実験用ダンプファイル（未）
4. アンケートデータ
```
現在2.がelan/以下に，3.がdumpfiles/に，4.がquestionnaire/以下にある．

## 2. 閲覧用ELANファイル
アノテーションや書き起こしを全て含んだeaf（ELAN annotation fomat）ファイ
ルである．
アノテーションツールELANで，実験参加者ビデオを読み込んで使用する．

elan/ 以下に，(実験参加者ID).eaf という名前で置かれている．実験参加者ID
は以下で示すYYMMGAANNの9文字である．  
　YYMM コーパスのバージョン．ここでは2010である．  
　G 実験参加者の性別．M（男性）もしくはF（女性）．  
　AA 実験参加者の年代．20から60まで．  
　NN 上記7文字と合わせてIDとなるように付番．
 
例えば2010F2001は「Hazumi2010の，20歳代のある女性のデータ」を意味する．

交換と呼ばれる単位ごとに，以下で示されるデータが付与されている．
詳しくは[概要説明ドキュメント](https://www.nii.ac.jp/dsc/idr/rdata/Hazumi/documents/HazumiOverview.pdf)を参照のこと．

#### 実験参加者の発話の書き起こし
#### システム発話とその対話行為
#### 心象アノテーション
複数の第三者が付与したもの (TS: Third Sentiment) と，実験参加者本人が付与したもの（振り返りアノテーション） (SS: Self Sentiment) がある．
#### 話題継続アノテーション

## 3. 実験用ダンプファイル
対話中のユーザ（実験参加者）の心象を含むラベルデータを予測するためのマルチモーダル機械学習実験を行うための利用を想定している．このファイルは， 機械学習の入力として，ユーザの音声，映像，発話内容（言語）から抽出したマルチモーダル特徴量（実数値），機械学習の出力として心象（本人・第3者）・話題継続アノテーションの値（連続値とカテゴリ値）を格納している．

### フォルダの構造とファイル：
dumpfiles/      
　├ 2010F2002.csv　  
　├ 2010F2003.csv　  
　:  
　:  

各ファイル（例：2010F2002.csv）は各セッションにおける参加者の発話対ごとの
マルチモーダル特徴量とアノテーションの値を含んでいる．計33人分のダンプファイルを格納している．

### 実験用ダンプファイル中のデータ説明：
各列はデータの属性，各行は1発話対で抽出された各特徴量の数値を格納している．  
1行目はデータの属性名を示す．


#### start(exchange), end(exchange):
ユーザの上半身動画（mp4）における発話交換（1発話対の）開始,終了時間 

#### TC1~TC3:
3名により付与されたtopic continuanceのアノテーション値.

#### TS1~TS3:
3名により付与されたthird sentimentのアノテーション値．

#### pcm_RMSenergy_sma_max ~ F0_sma_de_kurtosis: 
OpenSmileによって抽出された韻律特徴量. Config fileはIS09_emotion.conf.


#### 17_acceleration_max~AU45_c_mean: 
顔表情特徴量. 「17」のような数字はOpenFaceのlandmarkを示す. AUはaction unit.
landmark特徴量はOpenFaceから得られる2次元座標データ(30fps)をもとに目の周り, 口の周りなどの12点のフレーム間速度, 加速度をexchange区間ごとに求め最大値, 平均値, 標準偏差を特徴量とした. またexchange区間のAUの有無の平均を特徴量とした. 

#### Dialogue_act
システム発話のタイプ．
が格納されている．

#### ADJ～bert785： 
ユーザの発話から抽出された言語特徴量.
書き起こしデータ内のユーザ発話から特徴量を抽出した．Stanza NLPを使用して形態素解析を行い，1発話内に含まれる品詞ごとの単語数を計算している．
また，Wikipediaに含まれるテキストデータより学習したBERTモデルを利用して，
1発話（単語列）を786次元のベクトルに変換した特徴量も含む
以下で実装したBERTモデルを用いている．
https://github.com/yoheikikuta/bert-japanese


### マルチモーダルデータの同期方法：
ユーザの音声データ，映像データはZoomを通じて取得した．
音声・映像データはすでに時刻同期が行われている． 
言語特徴量（素性）は発話区間に対応するユーザ発話の書き起こしテキストから抽出した． 
詳しくは[概要説明ドキュメント]
(https://www.nii.ac.jp/dsc/idr/rdata/Hazumi/documents/HazumiOverview.pdf)を参照のこと．



詳しくは[概要説明ドキュメント](https://www.nii.ac.jp/dsc/idr/rdata/Hazumi/documents/HazumiOverview.pdf)を参照のこと．

# Authors
* 駒谷 和範（大阪大学 産業科学研究所） komatani@sanken.osaka-u.ac.jp
