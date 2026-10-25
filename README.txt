出る順英単熟語１級 — 配置と更新メモ

【GitHubに置くもの（リポジトリ直下）】
  index.html / sw.js / manifest.json
  icon-192.png / icon-512.png / icon-512-maskable.png
  data/unit1.js 〜 data/unit39.js（unit21.js 以降が TOEIC 単語）

【Unitを追加するとき（Unit 2 の例）】
  1. data/unit2.js を data フォルダに追加
  2. index.html の「<script src="data/unit1.js"></script>」の下に
       <script src="data/unit2.js"></script>
     を1行追加
  3. sw.js の  const DATA = ['data/unit1.js'];  を
       const DATA = ['data/unit1.js','data/unit2.js'];
     に変更し、CACHE の v1 を v2 に上げる
  ※ 全Unit数は index.html の EIKEN_UNITS（英検1級・20）と TOEIC_UNITS（TOEIC・19）で変更できます（UNITS_TOTAL は両者の合計）。
  ※ TOEIC 単語は内部番号 21 以降のファイル（unit21.js = 画面表示「TOEIC 1」、unit22.js = 「TOEIC 2」…）です。TOEIC 側の No. は各Unitの先頭から 1 始まりです。

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
  v15: TOEIC 990点用単語を追加。まず TOEIC 1（100語）を収録（全39 Unit予定＝英検1級20＋TOEIC 19）。TOEIC単語は英検1級の見出し語と重複するものを除外し、元の単語帳のページ順に約100語ずつUnit化。画面表示は「TOEIC 1」などのUnit名。表記ルールは既存Unitと同じ（【自】【他】・他動詞の助詞を【】に含める、熟語は idm）
  v16: TOEIC 2（102語）・TOEIC 3（102語）を追加。TOEIC は TOEIC 1〜3 の計304語を収録（全39 Unit予定のうち TOEIC 4〜19 が未収録）
     ※ 単語ID（no）は、英検1級＝Unit番号×1000＋No.、TOEIC＝100000＋(TOEIC番号)×1000＋No. で付与（学習記録の衝突を避けるため）
  v17: TOEIC 4〜7（計406語：TOEIC 4＝102語・TOEIC 5＝102語・TOEIC 6＝100語・TOEIC 7＝102語）を追加。TOEIC は TOEIC 1〜7 の計710語を収録（全39 Unit予定のうち TOEIC 8〜19 が未収録）。UNITS_TOTAL（39）は変更なし
     ※ 見出し語は元の単語帳のページ順（ページの切れ目で区切り）。既存の関連語・類義語欄にだけ載っていた語も独立した見出し語にし、意味が原形と同じ活用形（crumpled, prolonged, appalling など20語）は除外。熟語は各Unitに混在。例文はビジネス・職場の場面を中心にしています
  v18: TOEIC 8〜11（unit28〜31、計402語：100＋100＋100＋102）と TOEIC 12（unit32、100語）を追加。TOEIC は TOEIC 1〜12 の計1,212語を収録（全39 Unit予定のうち TOEIC 13〜19 が未収録）。UNITS_TOTAL（39）は変更なし
     ※ TOEIC 12 は索引の487ページ（bug）から529ページ（substandard）まで。ページの切れ目で区切り、既存の見出し語と重複する語は除外
  v19: TOEIC 13（unit33、102語）・TOEIC 14（unit34、100語）・TOEIC 15（unit35、102語）を画面に反映。TOEIC は TOEIC 1〜15 の計1,516語を収録（全39 Unit予定のうち TOEIC 16〜19 が未収録）。UNITS_TOTAL（39）は変更なし
     ※ TOEIC 13・14 はデータ（unit33.js・unit34.js）が入っていたが、index.html の読み込み（script タグ）と sw.js の DATA に未登録だったため、画面には TOEIC 12 までしか出ていなかった。今回あわせて登録して修正
     ※ TOEIC 15 は索引の602ページ（computer illiterate）から640ページ（digest）まで。ページの切れ目で区切り、既存の見出し語と重複する語（hybrid・compound・ruminate・mammal・foliage・sedentary・gene・parasite・bruise・acute・chronic・blister・distend・swelling・ingest・intake の16語）は除外。例文はビジネス・職場の場面を中心にしています
  v20: TOEIC 16〜19（unit36〜39、計410語：TOEIC 16＝102語・TOEIC 17＝103語・TOEIC 18＝103語・TOEIC 19＝102語）を追加。TOEIC は TOEIC 1〜19 の計1,926語を収録し、全39 Unit（英検1級20＋TOEIC 19）がすべて揃った。UNITS_TOTAL（39）は変更なし
     ※ 元の単語帳の641ページ（dress a wound）から799ページ（give a wide berth）まで。TOEIC 16＝641〜677ページ、TOEIC 17＝678〜719ページ、TOEIC 18＝720〜758ページ、TOEIC 19＝759〜799ページ。ページの切れ目で区切り、既存の見出し語と重複する語（cramp・slumber・delivery・immunity・ailment・wholesome・hygiene・antibiotic・mortality・rash・twinge・dehydrate・panacea・feud・pedestrian・brochure・enigma・chronicle・cuff・insinuation・metaphor・status quo・rhetoric・tantrum・jumble・crumple・eject・simmer・inexplicable・longevity・ditch・observance・preliminary・venue）の34語は除外。意味が原形と同じ活用形（dehydrated・thrashing・chafed）も除外。例文はビジネス・職場の場面を中心にしています
     ※ index.html の画面表示「全39Unit予定」を「全39Unit」に変更。sw.js の CACHE は v20

