### ✨ NFTを作成する

Metaplex CLI は、Candy Machine に利用可能な、NFT を発行するための簡単なツールです。

まずはすべての NFT データを格納するフォルダを作成することから始めましょう。

`app` が含まれているフォルダを開き、`assets` という名前の新しいディレクトリを作成します。ディレクトリ構造の一例です。

![無題](/public/images/5-Solana-NFT-drop/section2/2_2_1.png)

`assets` の中には、実際の NFT のアセット（ここでは画像）と、Metaplex が設定を行う際に必要となる特定の NFT のメタデータを記述した json ファイルという、互いに関連付けられたファイルのペアがあります。

ここにはいくつでも NFT をロードすることができますが、まずは3つの NFT をロードして、必要なものをすべて理解していきましょう。

どのアセットが各 json メタデータに対応しているかを把握するために、数字でシンプルな命名規則を設けます。

それぞれの PNG ファイルは、それぞれの json ファイルとペアになっています。以下2点に注意してください。

- 0から始めなければなりません。

- ネーミングに空白があってはいけません。

`assets` ディレクトリに、下記の通りファイルを作成してください。

```txt
// NFT #1
0.png
0.json

// NFT #2
1.png
1.json

// NFT #3
2.png
2.json
```

![無題](/public/images/5-Solana-NFT-drop/section2/2_2_2.png)

`0.json` は `0.png` に、 `1.json` は `1.png` にというようにです。

それでは、`json` ファイルを実際に作っていきましょう。

以下をコピーして `0.json` に貼り付けてください。

```json
// 0.json
{
  "name": "NAME_OF_NFT",
  "symbol": "",
  "image": "0.png",
  "properties": {
    "files": [
      {
        "uri": "0.png",
        "type": "image/png"
      }
    ],
    "creators": [
      {
        "address": "INSERT_YOUR_WALLET_ADDRESS_HERE",
        "share": 100
      }
    ]
  }
}
```

これは、各NFTを立ち上げるために必要となる基本情報です。

Metaplex はこのデータを、あなたに代わってオンチェーンで保存します。json ファイルには、`name`, `image`, `uri` などの属性があります。

上記と同様に、`1.json`、`2.json`にも貼り付けましょう。

"name"、  "image" 、"uri"、 "address" を変更することをお忘れなく！

さて、ここからはクリエイティブな作業が必要になります。

コレクションを作成するため、3つのランダムな NFT を考えてみてください。

まずは、あなたが好きな PNG を3枚選んでみてください。

好きなアルバムのカバー、好きなアニメのキャラクター、好きな映画のポスターなど、何でも構いません。

**お気に入りのものを3つ選んでください。**

※ 現在、CLI でサポートされているのは PNG のみです。

MP4、MP3、HTMLなどの他のファイルタイプについては、カスタムスクリプトを作成する必要があります。[こちら](https://github.com/metaplex-foundation/metaplex/issues/511) を参照してください。

最後に、`INSERT_YOUR_WALLET_ADDRESS_HERE` をあなたの Phantom wallet アドレスに置き換えてください（引用符「 `""` 」を忘れずに）。

`creators` 配列には複数のcreatorを設定できます。

これは NFT ビューに表示され、Solana Name Service 経由で接続されている場合は、Twitter ハンドル変わります。

🌟: Solana Name Service を利用する場合
- ウォレットアドレスと Twitter ハンドルを紐づけることができます。
-  `INSERT_YOUR_WALLET_ADDRESS_HERE` に Twitter ハンドルを代入しましょう。※ Twitter ハンドルとウォレットアドレスを紐づけるのには 0.01 SOL ほどかかります!

`share` 属性は、各クリエイターが受け取るロイヤリティの割合を表します。本プロジェクトではあなたが唯一のクリエイターなので、ロイヤリティのすべてを得られる設定です。
### 🙋‍♂️ 質問する

ここまでの作業で何かわからないことがある場合は、Discord の `#section-2` で質問をしてください。

ヘルプをするときのフローが円滑になるので、エラーレポートには下記の3点を記載してください✨
```
1. 何をしようとしていたか
2. エラー文をコピー&ペースト
3. エラー画面のスクリーンショット
```

---
次のレッスンに進んで、NFTを devnet にデプロイしていきましょう🎉
