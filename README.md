# ✏️ ことばみち (Kotobamichi)

> **English** | [日本語](#-日本語)

---

## English

A small puzzle game for children — draw paths with your finger to guide wandering creatures home.  
It runs as a single static HTML file, so you can publish it directly on GitHub Pages.

**▶ Play:** https://togakyo.github.io/Kotobamichi/

### How to Play

- Creatures **never stop walking**. Draw lines with your finger to build roads, ramps, and bridges, and deliver them to the house on the right.
- Tap **▶ Start** to release the herd. You can also draw the path first and start afterwards.
- Ink is limited. Use **Undo / Clear** to redraw.
- Switch stages with the **1 · 2 · 3** buttons in the bottom-right.

### Design Notes

Rather than a sprawling simulation, this game deliberately limits itself to a **single verb: "guide."**  
It is the mashup of two minimal ideas:

- **Draw a line → it becomes physics × steer a herd** — this is the backbone. Cause and effect are visible, so when you fail you just draw again. No reflexes needed.

Two extra "seeds" are layered in:

- **Words become materials** — the line you draw is made of "word-materials": `ふつう` (solid) / `つるつる` (slippery) / `ぽよん` (bouncy).
- **Rules you can flip** — the cards at the top read as sentences; tap a highlighted word and a law of the world changes (walk direction, gravity). Stage 3 cannot be cleared without using this.

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

- いきものは **とまらず歩き続ける**。ゆびで線を引いて道・坂・橋をつくり、右の家へ届ける。
- **▶ スタート** で群れが出てくる。先に道を描いてから出してもOK。
- インクは有限。**もどす / けす** で引き直せる。
- 右下の **1・2・3** でステージを切り替え。

### このゲームの設計メモ

「マイクラを超える育成ゲーム」ではなく、動詞を **「みちびく」ひとつ** に絞った尖った作りです。  
2つの単機能アイデアの掛け合わせで発想しています。

- **線を描くと物理になる × 群れを誘導する** … これが骨格。因果が目で見えるので、失敗しても描き直すだけ。反射神経はいりません。

さらに2つの「たね」を軽く仕込んでいます。

- **ことばが実体になる** … 描く線が「ことばの素材」になる。`ふつう`（かたい）/ `つるつる`（すべる）/ `ぽよん`（はねる）。
- **きまりを動かせる** … 上のカードがめくれる文章になっていて、単語をタップすると世界の法則が変わる（進む向き・重さ）。ステージ3はこれを使わないと解けません。

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
