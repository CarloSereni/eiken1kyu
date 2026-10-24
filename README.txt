出る順英単熟語１級 — 配置と更新メモ

【GitHubに置くもの（リポジトリ直下）】
  index.html / sw.js / manifest.json
  icon-192.png / icon-512.png / icon-512-maskable.png
  data/unit1.js 〜 data/unit20.js

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

【更新履歴】
  v2: Unit 2・3 を追加／マッチング・神経衰弱の時計表示を修正（時計の混線を解消）
  v3: Unit 4・5 を追加／関連語・派生語・反意語・類義語に品詞と意味を付記（全Unit）
  v4: Unit 6・7 を追加／前置詞（前）の品詞表示に対応
  v5: Unit 8・9・10 を追加（全10 Unit・1680語）
  v6: Unit 11 を追加（129語。全11 Unit・1809語）
  v7: Unit 12 を追加（129語。全12 Unit・1938語）／単語一覧に検索機能を追加／Unit選択時に横スクロールが左端に戻る不具合を修正
  v8: Unit 13 を追加（129語。全13 Unit・2067語）
  v9: Unit 14 を追加（129語。全14 Unit・2196語）
  v10: Unit 15 を追加（128語。全15 Unit・2324語）
  v11: Unit 16 を追加（128語。全16 Unit・2452語）
  v12: Unit 17 を追加（128語。全17 Unit・2580語）
  v13: 動詞の表記ルールを変更。意味の頭に【自】【他】を付与（両方ある場合は両方記載）。他動詞の例文和訳は助詞（を・に）を【】に含める。Unit1〜17の全動詞（979意味）を修正
  v14: Unit 18・19・20 を追加（Unit 18: 122語、Unit 19: 121語＝単語243語／Unit 20: 熟語212個。全20 Unit・3035語）。動詞の表記ルール（【自】【他】・他動詞の助詞）はv13と同じ
