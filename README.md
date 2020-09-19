# etl-weather
気象庁から気象データCSVをダウンロードします

コードは以下noteの有料部分にダウンロードリンクを公開させていただいております。
TODO: paste link

## 概要
![overview]](https://github.com/luckyriver0/etl-weather/blob/master/images/overview.png)

## データソース
気象庁<br>
https://www.data.jma.go.jp/obd/stats/data/mdrr/docs/csv_dl_readme.html

## 取得サイクル
毎日AM5:30(JST) に前日21時時点の気象データをダウンロードする。

## 取得データ
| 種類 | データ定義 | 保存先 |
| ---- | ---- | ---- |
| 最高気温 | [リンク](https://www.data.jma.go.jp/obd/stats/data/mdrr/docs/csv_dl_format_mxtem.html) |  {{rep_root}}/output/mxtemsadext/mxtemsadext00_{{yyyyMMddhhmm}}_000.00.csv |
| 最低気温 | [リンク](https://www.data.jma.go.jp/obd/stats/data/mdrr/docs/csv_dl_format_mntem.html) | {{rep_root}}/output/mntemsadext/mntemsadext00_{{yyyyMMddhhmm}}_000.00.csv |
| 降水量 | [リンク](https://www.data.jma.go.jp/obd/stats/data/mdrr/docs/csv_dl_format_predaily.html) |  {{rep_root}}/output/predaily//predaily00_{{yyyyMMddhhmm}}_000.00.csv  |

## バージョン情報

- [digdag](https://github.com/treasure-data/digdag) (0.9.42)
- [Embulk](https://github.com/embulk/embulk) (0.10.16)
- [Python](https://www.python.org/) (3.7.3)
