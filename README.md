# EOA Crypt For Tokyo Web3 Hackathon
## プロダクト概要
現状ほとんどのパブリックBC/分散型ストレージではセンシティブな情報が記録できません。  
多くのweb3プロダクトやサービスは、重要なデータ/ロジック部分をweb2領域に保持する必要があります。  

この問題が解決できればBCや分散型ストレージ、さらにはweb3領域活用の幅が大きく広がるという仮説のもと、EOAを基盤とした暗号/復号とその利用を考えました。  

【いわゆるweb3領域だけでどこまでデータの秘匿化が出来るのか?】【実用的範囲でweb2依存を減らし分散できるのか?】というテーマを検討していくきっかけにしたいという想いで、あえて  
【E2Eでの暗号/復号】【個人が関連データを保持/管理できる(自己主権)】【データおよびロジックはBC/分散型ストレージとクライアントサイドにのみ配置(リロケータブル)】【デプロイ後は開発者といえども一切関われない(Autonomos)】という要件定義のもとPoC実装を行いました。  

【永続化させたいデータを、誰かに「人質」に取られることなく秘匿化し、選択的開示や分散配置を行える仕組み】をみんなで継続して考え、実現していく最初の第一歩が『EOA Crypt』です。

## 概要動画
[!['概要動画'](https://i.ytimg.com/vi/FSYfN88Abqg/maxresdefault.jpg)](https://youtu.be/FSYfN88Abqg)

## テスト方法・手順
1. プロダクトデモページにアクセスし「Launch Dapps」ボタンを押してDappsのページに進んでください。  
[EOA Crypt デモページ](https://bafybeid77rns5df7nqp52tsjsfnegzk7gpxkrtd57uowllmamqpmx46zby.ipfs.w3s.link/)

1. 画面右上の「Connect wallet」を押してWeb3ウォレット(Metamask)を接続してください。  
利用にはガス代(0.0001GoerliETH程度)が必要となります。 (Ethereumのテストネットにつき無料)  
[GoerliETH Faucetページ](https://goerlifaucet.com/)　,  [GoerliETH マイニングページ](https://goerli-faucet.pk910.de/)  

1. 送信先を選択し、メッセージを入力して「送信」ボタンでメッセージの送信（共有）が可能です。  
(自分自身宛てに送れば秘匿化した情報の保存としてのユースケースが考えられます)  

1. 詳しくは、ヘルプページをご覧ください。  
[EOA Crypt ヘルプページ](https://ukishima.github.io/EOA-Crypt-For-Tokyo-Web3-Hackathon/docs/)

> 参考ガス量：
    - 登録時 45,471GAS
    - メッセージ送信時 基本GAS量 21,000GAS + 1宛先毎 3,000GAS 程度

## ローカル環境での検証手順と技術概要

1. 当リポジトリをクローンする。
1. LiveServerなどローカルサーバ環境で実行する。

※ コアモジュールであるmain.jsなどはIPFSでホストされているものを参照していますので、上記をそのまま実行した場合はローカルのjs等は呼ばれません。

EOA Cryptは、暗号化・復号のコア処理部においてJavaScript,WASM(C++)によって構成されており、
フロントエンド部は単なるHTML1ファイルで構成されているので、
リポジトリをクローンして「LiveServer」などで実行するだけで環境の構築が可能です。

また、EOA Cryptは(今回のデモ版においても)フロントエンドのロジックはIPFSへ配置、データはブロックチェーンおよびIPFSに保存されています。
よって特別にサーバを用意する必要はありません。  

## 概要
![EOACryptアーキテクチャー](https://github.com/ukishima/EOA-Crypt-For-Tokyo-Web3-Hackathon/blob/main/docs/overview/pic_architecture.jpg "EOACryptアーキテクチャー")

## Tech Stacks

| Category | Name |
| ---- | ---- |
| Protocol | Ethereum Goerli Testnet Network |
| Infrastructure | IPFS |
| Language | Html、CSS、Javascript、wasm（C＋＋）、Webpack、Solidity |
| Web2-Web3 Bridge | Ethers.js |

## Block Chain
Ethereum Goerli Testnet Network

## repository
https://github.com/ukishima/EOA-Crypt-For-Tokyo-Web3-Hackathon

## contract
https://goerli.etherscan.io/address/0x362bca0228740b2420d9df54b7f5bb53f266afd1

## Product Page（demo） * Hosted on IPFS
https://bafybeid77rns5df7nqp52tsjsfnegzk7gpxkrtd57uowllmamqpmx46zby.ipfs.w3s.link/

## Help Page
https://ukishima.github.io/EOA-Crypt-For-Tokyo-Web3-Hackathon/docs/

## Pitch Slide Page
[ピッチ資料](/docs/pitch/pitch.md)  
[11/12 DemoDayピッチ資料](/docs/1112Demoday_pitch/1112demoday_pitch.md)
