出る順英単熟語１級 — 配置と更新メモ

【GitHubに置くもの（リポジトリ直下）】
  index.html / sw.js / manifest.json
  icon-192.png / icon-512.png / icon-512-maskable.png
  data/unit1.js

【Unitを追加するとき（Unit 2 の例）】
  1. data/unit2.js を data フォルダに追加
  2. index.html の「<script src="data/unit1.js"></script>」の下に
       <script src="data/unit2.js"></script>
     を1行追加
  3. sw.js の  const DATA = ['data/unit1.js'];  を
       const DATA = ['data/unit1.js','data/unit2.js'];
     に変更し、CACHE の v1 を v2 に上げる
  ※ 全Unit数は index.html の UNITS_TOTAL（現在20）で変更できます。

【オフラインについて】
  初回は一度オンラインで開くと、全ファイルが端末に保存されます。以降は完全オフラインで起動します。
  発音（🔊）は端末の英語音声を使うため、端末に英語音声データが入っていない場合はオフラインで鳴らないことがあります。
