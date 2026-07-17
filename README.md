# ✏️ ことばみち (Kotobamichi)

> **English** | [日本語](#-日本語)

---

## English

A small puzzle game for children — draw paths with your finger to guide wandering creatures home.  
It runs as a single static HTML file, so you can publish it directly on GitHub Pages.

**▶ Play:** https://togakyo.github.io/Kotobamichi/

### How to Play

- Creatures **never stop walking**. Draw lines with your finger to build roads, ramps, and bridges, and deliver them to the house.
- Tap **▶ Start** to release the herd. You can also draw the path first and start afterwards.
- Ink is limited. Use **Undo / Clear** to redraw.
- Lines are made of **word-materials**: solid / slippery / bouncy, plus **command words** (marked 🔴) that creatures read and obey on contact — `Turn`, `Jump`, `Fast`.
- Clear levels to earn **★1–3** (deliver everyone for ★3). Stars are saved in your browser.
- **🍓 Fruits**: each level hides 3 fruits — route creatures through them. Collect all + ★3 for a **Perfect**.
- **🎩 Hats**: lifetime delivery milestones (10 / 25 / 50 / 100) unlock hats that creatures randomly wear.
- **📅 Daily**: a brand-new, procedurally generated level every day — same level for everyone. Clear it daily to grow your 🔥 streak, and share your result as an emoji grid.

### Design Notes

Rather than a sprawling simulation, this game deliberately limits itself to a **single verb: "guide."**  
It is the mashup of two minimal ideas:

- **Draw a line → it becomes physics × steer a herd** — this is the backbone. Cause and effect are visible, so when you fail you just draw again. No reflexes needed.

Two extra "seeds" are layered in:

- **Words become materials** — the line you draw is made of "word-materials": `ふつう` (solid) / `つるつる` (slippery) / `ぽよん` (bouncy).
- **Rules you can flip** — the cards at the top read as sentences; tap a highlighted word and a law of the world changes (walk direction, gravity). Stage 3 cannot be cleared without using this.

Three loops keep the game alive without a server or new hand-made content:

- **Stars (★1–3)** — replay old levels for perfect runs; progress persists via `localStorage`.
- **Procedural Daily** — the day number seeds a deterministic RNG (`mulberry32`), so everyone in the world gets the same fresh level each day, forever, with zero authoring cost.
- **Streak + emoji share** — Wordle-style: a 🔥 streak to protect, and a copy-paste result grid that advertises the game for free.

### Roadmap

Ideas welcome via issues/PRs — the whole game is one readable HTML file:

- [ ] More command words (`とまれ` stop, `まて` wait)
- [ ] Moving platforms / wind zones in daily generation
- [ ] Sound toggle & more expressive creature animations
- [ ] Level editor that exports a shareable URL

### File Structure

```
kotobamichi/
├─ index.html     ← The entire game (self-contained)
├─ README.md
├─ LICENSE        ← MIT (replace the name)
├─ .gitignore
└─ .nojekyll      ← Prevents GitHub Pages from running Jekyll
```

The only external dependency is Google Fonts (M PLUS Rounded 1c). It falls back to a system font without internet.

### Running Locally

Opening `index.html` directly in a browser works fine.  
To use a local server:

```bash
python3 -m http.server 8000
# → open http://localhost:8000
```

### License

MIT License. Free to modify and redistribute. See [LICENSE](LICENSE) for details.

---

## 日本語

歩き続けるいきものを、ゆびで描いた道でおうちへ導く、子ども向けの小さなパズルゲーム。  
1ファイルだけで動く静的サイトなので、GitHub Pages にそのまま公開できます。

**▶ あそぶ:** https://togakyo.github.io/Kotobamichi/

### あそびかた

- いきものは **とまらず歩き続ける**。ゆびで線を引いて道・坂・橋をつくり、家へ届ける。
- **▶ スタート** で群れが出てくる。先に道を描いてから出してもOK。
- インクは有限。**もどす / けす** で引き直せる。
- 線は「ことばの素材」でできている: ふつう / つるつる / ぽよん、さらに 🔴 じるしの **コマンドことば**(`もどれ` `とべ` `はやく`)は、いきものが触れると読んで従う。
- クリアすると **★1〜3** がもらえる(全員届けると★3)。★はブラウザに保存される。
- **🍓 フルーツ**: 各レベルに3つかくれている。いきものの通り道を工夫して集めよう。全部+★3で**パーフェクト**。
- **🎩 ぼうし**: 累計で届けた数(10・25・50・100ひき)でぼうしが解放され、いきものがランダムにかぶって登場する。
- **📅 デイリー**: 毎日自動生成される新しいレベル(みんな同じ面)。毎日クリアで 🔥 連続記録が伸び、結果を絵文字グリッドでシェアできる。

### このゲームの設計メモ

「マイクラを超える育成ゲーム」ではなく、動詞を **「みちびく」ひとつ** に絞った尖った作りです。  
2つの単機能アイデアの掛け合わせで発想しています。

- **線を描くと物理になる × 群れを誘導する** … これが骨格。因果が目で見えるので、失敗しても描き直すだけ。反射神経はいりません。

さらに2つの「たね」を軽く仕込んでいます。

- **ことばが実体になる** … 描く線が「ことばの素材」になる。`ふつう`（かたい）/ `つるつる`（すべる）/ `ぽよん`（はねる）。
- **きまりを動かせる** … 上のカードがめくれる文章になっていて、単語をタップすると世界の法則が変わる（進む向き・重さ）。ステージ3はこれを使わないと解けません。

サーバも追加コンテンツ制作もなしで遊び続けられるよう、3つのループを仕込んでいます。

- **★評価 (1〜3)** … 全員救出をめざして再挑戦。進捗は `localStorage` に保存。
- **自動生成デイリー** … 日付をシードにした決定的乱数 (`mulberry32`) でレベルを生成。世界中で同じ面が毎日、制作コストゼロで供給される。
- **連続記録 + 絵文字シェア** … Wordle方式。守りたくなる 🔥 ストリークと、貼るだけで宣伝になる結果グリッド。

### ロードマップ

ゲーム全体が読みやすい1つのHTMLファイルなので、Issue / PR 歓迎です。

- [ ] コマンドことばの追加（`とまれ`・`まて` など）
- [ ] デイリー生成に動く足場・風ゾーン
- [ ] サウンドON/OFF、いきもののアニメーション強化
- [ ] URLで共有できるレベルエディタ

### ファイル構成

```
kotobamichi/
├─ index.html     ← ゲーム本体（これ1つで完結）
├─ README.md
├─ LICENSE        ← MIT（名前を書き換えてください）
├─ .gitignore
└─ .nojekyll      ← GitHub Pages が余計な処理をしないための空ファイル
```

外部依存は Google Fonts (M PLUS Rounded 1c) のみ。ネットがなくても代替フォントで動きます。

### ローカルでの確認

ブラウザで `index.html` を直接ひらくだけでも動きます。  
簡易サーバを使うなら:

```bash
python3 -m http.server 8000
# → http://localhost:8000 を開く
```

### ライセンス

MIT License. 自由に改変・再配布できます。詳細は [LICENSE](LICENSE) を参照。
