# Street-tree-management
## 本文
## 題名
## 目次
1. はじめに
2. 研究方法
3. 考察
4. 結論
5. 参考文献

## 1. はじめに
都市における街路樹は、街の景観向上（シンボルツリー、新芽・花・紅葉などで四季を感じるなど）、生活環境の保全（騒音低下、夏の緑陰確保、ヒートアイランド現象の抑制、大気の浄化）、交通安全（歩道と車道の分離、眩しさを遮る）、防災（火事の延焼を防ぐ）などの役割がある。しかし自然界ではなく、道路沿いという環境に植えられた現代の街路樹は、道路標識の視認性確保のため強剪定されたり、強風・地震・積雪などで倒れたりし、歩行者が人命を奪われたり、交通障害を起こしたりする。また、災害時は避難や救助活動の障害になることもある。日本では住宅開発が進んだ1960年～1980年代に大量に植えられた街路樹が老齢化し、倒木被害などの問題も顕在化しつつある。植えられた街路樹は管理を怠らず日常的な点検・剪定・改善措置の実行などのメンテナンスをしっかりと行い、異常や危険などの問題を回避する必要がある。そのためには、行政だけでなく、市民も日頃から身近な街路樹に対し関心を持ち行政と市民の協働が望まれる。
現在の街路樹管理の問題点として以下の点があげられる。
1. 紙帳簿で樹木の管理情報を記録し、街路樹をGISを利用したデジタル地図にマッピングしていない自治体がほとんどである。また、街路樹についてオープンデータを提供している自治体は少なく、提供している自治体も樹種とその本数などに限られているものがほとんどである。
2. 樹木医による診断や樹木健全度調査は多大なコストと労力が必要であり、同じ街路樹の診断調査を毎年実施するのはむずかしい。　
3. 異状木に対し住民から街路樹専門に情報提供（苦情等）を受ける方法が確立されていない。スマートフォン用アプリを使用している自治体もある。（例　相模原市の「パッ！撮るん」）しかし、これらアプリは道路全般の障害通報が主目的で街路樹専門ではない。
4. 街路樹管理を担当する職員数の不足。  

上記問題点を解決するため、本研究では誰でも簡単に利用・編集できるOpenStreetMap　(以下OSM）に街路樹をマッピングし、街路樹の位置情報、属性を共有し、Mapillaryで街路樹の時系列変化を記録、Local Wikiで樹木（特に問題のある樹木）の生育状態の経時的変化を過去の写真も利用し記録する方法をとった。街路樹管理支援のため行政と市民が使いやすく継続して利用できる状況の構築を試みた。

## 2. 方法
2-1  [OpenStreetMap](https://ja.wikipedia.org/wiki/%E3%82%AA%E3%83%BC%E3%83%97%E3%83%B3%E3%82%B9%E3%83%88%E3%83%AA%E3%83%BC%E3%83%88%E3%83%9E%E3%83%83%E3%83%97) とは

OpenStreetMap(以下OSM)は自由に利用でき、地物の地理情報を自由に編集できる機能を持った世界地図を作る世界的な共同プロジェクトである。提供されたデータはOpen Database(ODbl)1.0のもと再利用可能である。

2-2 [Go Map!!](https://wiki.openstreetmap.org/wiki/JA:Go_Map!!)とは

OpenStreetMap内の情報を編集したり新規作成できるiphone用のiOSアプリ。Nodeを素早く登録できるため、フィールドでの個々の街路樹の位置情報登録に使用した。

2-3 対象街路樹とOSM入力方法

横浜市都筑土木事務所が2018年度に樹木医により街路樹診断をした樹木を中心に1100本余りの樹木をOSMにGo Mapを使用してマッピングした。樹種はケヤキ、クス、ソメイヨシノ、ユリノキ、ヤマザクラ、イチョウ、ハクウンボク、ハナミズキ、アラカシ、サクラ（八重桜）、シラカシ、カツラ、エンジュ、アメリカフウ、こぶし、サルスベリ、シダレザクラ、ナンキンハゼ、メタセコイア、ナツツバキ、モチノキ、ハクモクレン、フジ、不明など25種。サクラは種がはっきりわかるものはヤマザクラ、ヨウコウザクラ、シダレザクラなど分けた。  

![list-1.png](https://user-images.githubusercontent.com/15658355/71581253-b22a2400-2b47-11ea-801a-408b1b45ebe7.png)
 図1　OSM入力　樹木リスト 


Tagの入力にはOpenStreetMapのtreeのTagつけを参考にdenotation, genus, genus:ja, leaf_cycle, leaf_type, natural, source, species, species:ja, tree:ref の10keyとvalueを入力した。tree:refには2018年度の樹木診断で表示された樹木番号を入力した。樹木診断されなかった樹木で番号がないものも、現地調査で樹木に番号タグが付いていたものはそれを入力した。  

<img src="https://user-images.githubusercontent.com/15658355/71581533-f964e480-2b48-11ea-89ea-ccc69618375f.jpg" height="250px">  <img src="https://user-images.githubusercontent.com/15658355/71581540-fd910200-2b48-11ea-859f-76f91ead1779.jpg" height="250px">   
画像1  Go Mapのスマホ画

2-4 [Mapillary](https://www.mapillary.com/)とは

スマホなどで撮影した写真に位置情報を付加し写真共有をするサービスのアプリ。クラウドソーシング方式で世界のあらゆる場所を投稿できるが、最近はほとんどストリートビュー作成に重きを置いている。ライセンスはCC-BY-SA.  



参考文献：  

https://wiki.openstreetmap.org/wiki/JA:Tag:natural%3Dtree  

https://wiki.openstreetmap.org/wiki/Key:denotation
