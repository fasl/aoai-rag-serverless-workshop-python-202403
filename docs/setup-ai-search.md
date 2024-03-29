# 🧪 1. AI Search のセットアップ

AI Search は、フルテキスト検索やベクター検索などの検索機能を提供するフルマネージドの PaaS です。ここでは、AI Search を使って以下を実践します。

- 1-1. AI Search のリソース作成
- 1-2. インデックスの作成

## 1-1. AI Search のリソース作成

Azure portal (`portal.azure.com`) を開き、上部の検索で「ai search」と入力して表示される "AI Search" をクリックします。

![image](./images/1-1-1.png)

<br>

AI Search の一覧が表示されますので、"作成" をクリックします。

![image](./images/1-1-2.png)

<br>

以下を参考に入力し、"確認および作成" をクリックします。

 No. | 項目 | 入力内容
---: | --- | ---
1 | サブスクリプション | 任意のサブスクリプションを選択します。
2 | リソースグループ | Azure OpenAI Service を作成したときに作ったリソースグループを選択します。
3 | サービス名 | 任意の名称を入力します。これはグローバルで一意の名称になる必要があります。例:「srch-xxxx-handson202309」( "xxx" は自分のハンドルネームや任意のプロジェクト名など) 。
4 | 場所 | 任意の場所を選択します。下図は東日本リージョンである「Japan East」を選択しています。
5 | 価格レベル | "Free" を選択します。Free が選択できない場合は、"基本" を選択します。

![image](./images/1-1-3-free.png)

<br>


検証が完了したら、"作成" をクリックします。もしエラーが起きた場合は、エラーの内容を確認して修正してください。

![](./images/1-1-4.png)

<br>

作成は30秒程度でできます。完了したら、"リソースに移動" をクリックします。

![image](./images/1-1-5.png)

<br>

## 1-2. インデックスの作成

AI Search のリソースを表示して、概要の上部にある "インデックスの追加" > "インデックスの追加" をクリックします。

![image](./images/1-2-1.png)

<br>

インデックスの作成画面が表示されます。インデックス名に「azure」と入力します。

![](./images/1-2-2.png)

<br>

次に "フィールドの追加" をクリックしてフィールドを追加します。以下図を参考に3つのフィールドを追加します。

フィールド名 | 型 | 取得可能 | フィルター可能 | ソート可能 | ファセット可能 | 検索可能 | アナライザー
--- | --- | :---: | :---: | :---: | :---: | :---: | ---
title | Edm.String | ✅ | - | - | - | ✅ | 日本語 - Microsoft
category | Edm.String | ✅ | ✅ | - | ✅ | ✅ | 日本語 - Microsoft
content | Edm.String | ✅ | - | - | - | ✅ | 日本語 - Microsoft

<br>

最後に、ベクターの値を格納するためのフィールドを追加します。入力は以下図を参考にします。

![image](./images/1-2-3.png)

<br>

ベクター構成なしと表示されている下にある "作成" をクリックします。以下図の画面が表示されますのでデフォルトの値のままで "保存" をクリックします。フィールドの追加に戻るので、もう一度 "保存" をクリックします。

> ※ この値に関してご興味がありましたら、以下のドキュメントをご参照ください。
>
> - [ベクター検索の概念 | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/search/vector-search-overview#why-use-vector-search)

![image](./images/1-2-4.png)

<br>

最終的に以下のようなインデックスを構成したことを確認して左下の "作成" をクリックします。

![image](./images/1-2-5.png)

<br>

## 📚 参考情報

- [Azure AI Search の概要 | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/search/search-what-is-azure-search)
- [Azure AI Search のインデックス | Microsoft Learn](https://learn.microsoft.com/ja-jp/azure/search/search-what-is-an-index)

---
[📋 目次](../README.md)
