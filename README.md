# eccube-4.0.6_purchaseRestrict_csvImport

# プラグイン[購入制限プラグイン(4系)]導入後に商品CSV登録を行う場合のカスタマイズ方法（参考）
1. CSV雛形ファイルダウンロードへ購入制限IDカラムを追加する
2. 既存プログラムを改修しエラーや登録処理を追加する
3. エラー時のメッセージを追加する
※本プログラムは4.0.6-p1をベースにしています。各環境で異なる場合があるので上書きはせず参考にしてください

### 1.CSV雛形ファイルダウンロードへ購入制限IDカラムを追加する
ダウンロードするカラム一覧はDBに保存されている為レコードを追加します
```
INSERT INTO dtb_csv ( csv_type_id, entity_name, field_name, disp_name, sort_no, enabled, create_date, update_date, discriminator_type ) values ( 1, 'Eccube\\Entity\\Product', 'purchase_restrict_id', '購入制限ルールID', 99, true, now(), now(), 'csv');
```

### 2.既存プログラムを改修しエラーや登録処理を追加する
下記ファイルを変更します。
```
src/Eccube/Controller/Admin/Product/CsvImportController.php
'''
変更箇所の詳細は下記を確認ください

※Customize/ 以下へ移動する方法は記載していません。上記ファイルを参考にしてください。

### 3.エラー時のメッセージを追加する
下記ファイルを変更します。
```
src/Eccube/Resource/locale/messages.ja.yaml
src/Eccube/Resource/locale/messages.en.yaml
```
変更箇所の詳細は下記を確認ください

※Customize/ 以下へ移動する方法は記載していません。上記ファイルを参考にしてください。


プログラムの改修は自己責任にて行いください


