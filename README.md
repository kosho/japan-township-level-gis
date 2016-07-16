# Japan Township GIS Information - Elasticsearch Indexing Sample

## Data Source

- Copyright: National Land Information Division, National and Regional Policy Bureau of Japan
- License: [位置参照情報利用約款](http://nlftp.mlit.go.jp/isj/agreement.html)

## Files

- README.md - this file
- japan-township-level-gis-logstash.conf - Logstash config
- japan-township-level-gis-template.json - index template
- 3_2014.csv - sample CSV file [大字・町丁目位置参照情報　国土交通省](http://nlftp.mlit.go.jp/isj/)

## Usage

1. Download a CSV file from [the GIS download service](http://nlftp.mlit.go.jp/isj/)
2. Configure the elasticsearch output plugin setting of `japan-township-level-gis-logstash.conf` to point out an appropriate Elasticsearch node to ingest the data
3. Run logstash as below

  $ cat 13_2014.csv | iconv -f sjis -t utf-8 | logstash -f japan-township-level-gis-logstash.conf

