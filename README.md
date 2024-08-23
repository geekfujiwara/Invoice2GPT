# Invoice2GPT
請求書読み取りを生成AIにより自動化するソリューションです。


![image](https://github.com/user-attachments/assets/67f93352-ef38-400a-8a26-1340aedd5ec8)

- オンプレ会計システム連携部分についてはソリューションに含めておりません。

# デモ動画
## オンプレ会計システム連携無し板(提供しているソリューション)

https://github.com/user-attachments/assets/53a71f03-bad6-4587-99da-29b36c422cbe

## オンプレ会計システム連携あり版(活用イメージとしてのデモ動画のみの提供)

実行される環境によって、差異が考えられるため、オンプレミス連携のRPA部分はソリューションに含んでおりません。各自、連携先のシステムに合わせてフローを修正してください。

https://github.com/user-attachments/assets/db7bd79a-43a9-433d-8575-c3bb123008c2

# ソリューションの構成
以下のコンポーネントが含まれています。

* キャンバスアプリ
* 読み取った請求データを登録するDataverseテーブル
* 承認ワークフローと会計システム連携用のPower Automate クラウドフロー
* データを抽出するAIプロンプト

![image](https://github.com/user-attachments/assets/28b82ad5-e01e-4490-a72c-04dfe28b3834)

AIプロンプトは請求書に特化するように調整されており、以下の項目を抽出します。
- 請求額
- 請求日
- メールアドレス
- 請求先の会社名
- 請求書番号

![image](https://github.com/user-attachments/assets/ea41e4af-58d5-471f-b7e9-f73f19a6e71f)

# 特長

## モバイル対応

モバイルデバイスでもカメラを起動して写真を撮影し、ドキュメントをアップロードすることができます。

![image](https://github.com/user-attachments/assets/f59df029-9b9c-4864-ac75-d22710936221)

OCR部分を非表示にして抽出結果を確認することができます。

![image](https://github.com/user-attachments/assets/1651863d-fec1-417c-9cf7-0131ce4140e0)

## 抽出過程の表示

普段は非表示ですが、必要に応じてOCRの結果、JSONへの抽出ログを確認することができます。

![image](https://github.com/user-attachments/assets/cc8bcf9a-a2b2-4a63-a60d-e7d3ae485a64)



# 前提条件

* Power Apps Premium ライセンスが必要です。
* 本ソリューションには含まれておりませんが、もし、RPAの機能を実装する場合Power Automate Premium のライセンスも必要です。

# ソリューションのインポート方法
Azure 等のPower Plarform から見て外部リソースを使用していないため、ソリューションをインポートするだけで使えます。

1. [リリース](https://github.com/geekfujiwara/Invoice2GPT/releases/tag/Invoice2GPT)より入手したソリューションをPower Apps 作成者ポータルにてインポートします。

![image](https://github.com/user-attachments/assets/dbca5c1c-28a8-4f0a-b712-177172c8799e)


2. インポート完了後、ソリューションはマネージドソリューションに提供されていますので、マネージドのタブからソリューションを選択します。

![image](https://github.com/user-attachments/assets/d54ead3d-0196-4050-b01b-0fff8f897acb)


3. すべてのカスタマイズを公開します。

![image](https://github.com/user-attachments/assets/740b0940-3ac5-4ab1-822d-233bf1dceaba)

4. フローが有効になっていることを確認します。もし有効になっていなかった場合、フローを有効化します。

![image](https://github.com/user-attachments/assets/0438e7bb-88ae-4f6b-a3da-6276e16efae0)


> [!Note]
> フローには、オンプレミスのシステムや、APIが提供されている会計システム等に連携できるようにフロー内にデモのステップが用意されています。
>
>  ![image](https://github.com/user-attachments/assets/6616bfc2-0695-472b-b986-dc9e38795183)
>
> 「伝票番号デモ」の部分を請求データを連携したいシステムに置き換えて利用してみてください。
>
> 例えばこちらはPower Automate for desktop のフローに置き換え、オンプレミスのシステムにデータ連携するパターンで作成した例です。
>
> ![image](https://github.com/user-attachments/assets/1b5fa1e2-efc4-42ed-916b-9ce8458bc765)


## サンプルデータ
テスト用に必要でしたら、[請求書のサンプルデータ](https://github.com/geekfujiwara/Invoice2GPT/releases/tag/SampleInvoice)をご利用ください。

以上
