# Radikoの番組を録音するスクリプト
指定された日付と放送局の1日分の番組音声データをローカルファイルに保存します。

## 使い方
```
radiko [-d 日付] [-s ステーションID] [-l]
-d 日付: 番組日付 yyyymmdd形式
-d [-+]数字: 相対日付（例 -1 -> 前日、+7 -> 1週間先）
-s ステーションID: 放送局を表すコード（例 J-WAVE -> FMJ）
-l: 番組表のみ保存
```

## 出力ファイル名
音声データ
```
{放送日}-{開始時刻}-{終了時刻} [{局名}] {番組名}.m4a
```

番組表
```
{放送日} {局名}.xml
```

## 前提
- ffmpegが使える
- xmllintが使える
- echoコマンドに-nオプション（改行を出力しない）がある

- 個人的な視聴目的でのみ使用します

## macOS
```
brew install ffmpeg
```

## Respberry Pi (Debian Linux)
```
sudo apt install ffmpeg
sudo apt install libxml2-utils
```

## ステーションID
RadikoのAPIから取得できます。
https://radiko.jp/v3/station/region/full.xml

Radikoの放送局一覧からリンクしている各放送局の番組表のURLにもステーションIDが入っています。
https://radiko.jp/index/