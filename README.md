# Piholeを初期化したときのメモ
デフォルト設定でブロックされないドメイン・ブロックされるドメインをまとめとく<br>
**独自解釈です参考にしないでください**
## 前提知識
### ブロックできる広告
* Webサイトに組み込まれた広告
* Google AdSenseなど外部から呼び出す（？）広告
* 外部から呼び出す（？）よう設計されたアプリ内の広告
  * Vo◯doo製のゲームアプリ 
### ブロックできない広告
* 独自の広告サービス（？）で配信される広告
  * Youtube
  * Twitter
  * Spotify
## Blacklist
|サービス名|ドメイン|ワイルドカード|登録理由|メモ|
|:---:|:---:|:---:|:---:|:---:|
|simeji|shimeji.me|True|情報漏えい防止|
|BOOST NEXT|boost-next.co.jp|True|エロ広告|
|GENIEE SSP|gsspat.jp|True|エロ広告|日本企業っぽい|
|STRIPCHAT|xxxvjmp.com|True|エロ広告|リダイレクト型|
|？？？|xxxnewvideos|True|エロ広告|ドメイン？|
|？？？|vpotyflfox.com|True|エロ広告|AdGuardでもヒット|
|Periscope|pscp.tv|True|エロ広告|例外はWhitelist|
|？？？|godpvqnszo.com|True|マルバタイジング|アクセス厳禁|
|？？？|offvmuf.com|True|たぶん|AdGuardでもヒット|
|？？？|thench.net|True|推定エロ広告|検索結果なし|
|FIVE|fivecdm.com|True|行動ターゲティング広告|[KDDI](https://www.kddi.com/app-policy/ios/app-policy-targeting-newspass-1.5.html)参照|
|EZmob DSP|ezmob.com|True|エロ広告|Pornhubで利用？|
|？？？|ondigitalocean.app|True|偽警告|おもしろいけど|
|Pixiv|ads-pixiv.net|True|Pixiv広告|99%カット成功|

### エロ広告について
* エロサイト特有のいかがわしいバナー広告やポップアップの**内容**を表示させることは防ぐことができる
  * 内容を消すだけで出現を防ぐことはできない
* 意図しないリダイレクトは最初のドメインをブロックすることで防ぐことができる 
* エロサイトだけではなく5chやまとめサイトでも確認済み

## Whitelist
|サービス名|ドメイン|ワイルドカード|メモ|
|:---:|:---:|:---:|:---:|
|Youtube|s.youtube.com|False|ブロックしても意味がない|
|Unity|unity3d.com|True|3Dゲームの不具合を招く（かも）|
|Periscope|proxsee.pscp.tv|False|Twitter Spaces|

## 参考
2023年3月19日採録
* [pi-hole](https://github.com/pi-hole)（公式GitHubリポジトリ）
* [Malwarebytes](https://www.malwarebytes.com)
  * [godpvqnszo.com](https://www.malwarebytes.com/blog/detections/godpvqnszo-com) - MalwarebytesLABS
  * [ondigitalocean.app](https://www.malwarebytes.com/blog/detections/ondigitalocean-app) - MalwarebytesLABS
* [行動ターゲティング広告について](https://www.kddi.com/app-policy/ios/app-policy-targeting-newspass-1.5.html)（KDDI）
