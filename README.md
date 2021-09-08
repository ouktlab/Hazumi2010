# Hazumi2010
Osaka University Multimodal Dialogue Corpus (Hazumi2010)

Hazumi2010では以下のファイル群を公開している（もしくは公開予定）．
```
1. ビデオデータ（未）
2. 閲覧用ELANファイル
3. 実験用ダンプファイル（未）
4. アンケートデータ（未）
```
現在2.のみがelan/以下にある．

## 2. 閲覧用ELANファイル
アノテーションや書き起こしを全て含んだeaf（ELAN annotation fomat）ファイ
ルである．
アノテーションツールELANで，実験参加者ビデオを読み込んで使用する．

elan/ 以下に，(実験参加者ID).eaf という名前で置かれている．実験参加者ID
は以下で示すYYMMGAANNの9文字である．  
　YYMM コーパスのバージョン．ここでは2010である．  
　G 実験参加者の性別．M（男性）もしくはF（女性）．  
　AA 実験参加者の年代．20から70まで．  
　NN 上記7文字と合わせてIDとなるように付番．
 
例えば2010F2001は「Hazumi1911の，20歳代のある女性のデータ」を意味する．

交換と呼ばれる単位ごとに，以下で示されるデータが付与されている．
詳しくは[概要説明ドキュメント](https://www.nii.ac.jp/dsc/idr/rdata/Hazumi/documents/HazumiOverview.pdf)を参照のこと．

#### 実験参加者の発話の書き起こし
#### システム発話とその対話行為
#### 心象アノテーション
複数の第三者が付与したもの (TS: Third Sentiment) と，実験参加者本人が付与したもの（振り返りアノテーション） (SS: Self Sentiment) がある．
#### 話題継続アノテーション


詳しくは[概要説明ドキュメント](https://www.nii.ac.jp/dsc/idr/rdata/Hazumi/documents/HazumiOverview.pdf)を参照のこと．

# Authors
* 駒谷 和範（大阪大学 産業科学研究所） komatani@sanken.osaka-u.ac.jp
