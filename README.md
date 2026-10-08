# 金匱要略（新編金匱要略方論）原文・注・現代語訳

『金匱要略』（『新編金匱要略方論』，四部叢刊本）の原文を，条文（または段落）ごとの小さな単位に分け，資料間の異同（校異）・校訂，徐彬『金匱要略論註』の注（原文），現代語訳（日本語・英語）と組み合わせたもの。人が読むためだけでなく，LLM が読みやすいことを目指して，1単位を1ファイルにし，ファイルの頭に機械で読める情報（YAML）を付けている。

全篇（782単位）について，句読点を付けた原文，校異・校訂・注釈，徐彬注（原文），日本語訳・英訳（原文と徐彬注の訳，解説）がそろっている。姉妹編として[傷寒論（宋本）原文・注・現代語訳](https://github.com/medicalcloud/shokanron)がある。

## 構成

```
NN_篇名/
  index.md      篇の説明，篇首の注，単位の一覧
  NNN.md        原文（句読点つき）＋校異・校訂・注釈＋徐彬注（原文）
  NNN.ja.md     日本語訳：原文の訳・徐彬注の訳・解説
  NNN.en.md     英訳：同じ内容の英語版
```

- 篇は 00（林億らの序と兪橋の識語），01〜25（本文25篇），26（目録）。
- 単位の番号：01〜25 は篇ごとの条文の番号。条文の直後の方（構成生薬・煎じ方）も同じ単位に入れ，附方は方ごとに1単位とした。中国の教科書などの条文番号とは一致しないことがある。00・26 は段落の番号（`p001` など）。

### ファイルの頭の情報（YAML）

| キー | 内容 |
|---|---|
| book | 書名 |
| chapter / chapter_title | 篇の番号と篇名 |
| unit | 単位の番号（ファイル名） |
| clause | 条文の番号（01〜25 のみ） |
| paragraphs | 元の本文での段落の番号 |
| formulas | この単位に出る方の名 |
| title | 単位の題 |
| punctuated | 原文に句読点を付けたか |

訳のファイル（`.ja.md` `.en.md`）の頭には `unit` `clause` `lang` `source`（対応する原文のファイル）と，方があれば `formulas` を付けている。

### 訳と解説の書き方

- 訳は直訳を基本とし，補った語は〔〕に入れた。
- 解説は一般的な解釈を独自の言葉でまとめたもので，現代の注釈書からの引用はしていない。
- 底本の字が疑わしいところは，訳を底本どおりにして〔〕や解説で注記した。
- 『傷寒論』と重なる条文は，解説で宋本『傷寒論』の条文番号を示した。
- 徐彬注が後の単位にまとめて付いているときは，その旨を解説に記した。
- 英訳の用語は傷寒論と同じ（六経は taiyang などの拼音，方は「Gegen tang (Pueraria Decoction)」の形，生薬は拼音）。

## 本文と資料

- **本文の元（底本）**：Kanripo（漢籍リポジトリ）の『新編金匱要畧方論』（四部叢刊本，KR3e0007）を，日本の新字体に変換したもの（字体の方針は `字体と変換の方針.md`）。外字は KR-Gaiji の字形で字を当てた。
- **照合した資料**：Wikisource「金匱要略方論」「金匱要略」，儒道中医網，殆知閣，Kanripo の徐彬『金匱要略論註』（KR3e0006）。
- **補い**：底本の丁が欠けている箇所（第18篇末〜第19篇初め，第23篇の初め）は，Wikisource「金匱要略方論」によって補い，【補】と記した。
- **校異**：資料の間の字句の違い。「X は「…」に作る」の形で，どの資料かを示す。字体だけの違い・句読点・他の資料の欠落は記していない。
- **校訂**：本文を改めたところ（152か所）。他の5資料がそろって底本と違うところだけを改め，元の字句と根拠を【校訂】に記した。
- **徐彬注**：Kanripo の『金匱要略論註』から，本文と注を機械的に分けて取り出し，底本の段落に位置を合わせたもの。境目や位置の誤りがありうる。位置を合わせられなかった注は篇の `index.md` に置いた。徐彬本は第22篇の後半と第23篇の後半が欠けており，その部分には注がない。

## 権利とライセンス

- **古典の文**（『金匱要略』の本文，徐彬注，序・識語などの文）：パブリックドメイン。電子テキストの元になった資料の文を引くときは出典を示している。
- **このプロジェクトで新しく書いたもの**（句読点，校異・校訂・注釈の説明，日本語訳・英訳，解説，YAML の情報など）：LLM（Claude）を使って作成したもの。[クリエイティブ・コモンズ 表示 4.0 国際（CC BY 4.0）](https://creativecommons.org/licenses/by/4.0/deed.ja)で提供する。利用・改変・再配布・商用利用ができる。利用するときは出典として「金匱要略（新編金匱要略方論）原文・注・現代語訳（Hideaki Takata）」とこのリポジトリを示すこと。詳しくは `LICENSE`。
- 訳と解説は LLM によるもので，誤りがありうる。臨床に用いる判断の根拠にはしないこと。

---

**English summary**: The *Jingui yaolüe* (Essential Prescriptions of the Golden Cabinet; *Xinbian Jingui yaolüe fanglun*, Sibu congkan edition), split into small units (clauses with their formulas for chapters 1–25; paragraphs for the preface and table of contents). Each unit file contains the classical text (Japanese shinjitai), textual variants among sources, editorial emendations, and Xu Bin's commentary (*Jingui yaolüe lunzhu*); each unit also has Japanese (`.ja.md`) and English (`.en.md`) translations of the text and commentary, with explanatory notes. Each file starts with YAML metadata. A companion project covers the [Shanghan lun](https://github.com/medicalcloud/shokanron).

**License**: The classical texts are in the public domain. Punctuation, notes, translations, and other material newly written for this project (with the help of an LLM, Claude) are licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Translations and notes may contain errors and are not medical advice.
