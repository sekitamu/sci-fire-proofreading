# sci-fire-proofreading

日本語の小説を、本文を変更せずにチェックする Agent Skill です。
明白な誤りと要確認・提案を分け、文学的な省略、倒置、反復、話者の口調を尊重します。

## チェックする内容

1. 誤字・脱字・衍字
2. 助詞の重複や不足
3. 原稿の表記と体裁
4. 漢字とひらがなの表記ゆれ
5. 人名・地名・固有名詞の表記ゆれ

指摘には原文、位置、根拠、修正候補または確認事項を付けます。
本文への修正は実行しません。
校正結果は AI による候補であり、見落としや誤検出は著者による確認が必要です。

## ファイル構成

```text
sci-fire-proofreading/
├── SKILL.md
├── README.md
└── references/
    ├── manuscript-format.md
    └── submission-format.md
```

`SKILL.md` と `references/` を一緒に配置して使います。
ほかのスキル、作品の本文、人物設定への依存はありません。
同梱の体裁ルールは Sci-Fire 式の既定値です。
対象作品に明示的な規則があればそちらを優先し、ディレクトリ構成やファイルの連結・出力先は指定しません。

## 別のプロジェクトで使う

一度だけ使う場合は、保存した `SKILL.md` のパスを指定して読み込ませます。

```text
保存した sci-fire-proofreading/SKILL.md を読み、指定した原稿を校正してください。
本文は変更せず、明白な誤りと要確認・提案を分けて報告してください。
```

Codex のプロジェクト用スキルとして使う場合は、プロジェクトの `.agents/skills/sci-fire-proofreading/` にこのディレクトリの内容を置きます。
すべてのプロジェクトで使う場合は、ユーザー用の `~/.agents/skills/sci-fire-proofreading/` に置きます。
Windows では `~` はユーザーフォルダを表します。
導入先にはどちらか一方を選びます。

導入後の依頼例：

```text
$sci-fire-proofreading
指定した本文ファイルを校正してください。
作品の表記ルールと人物一覧も参照し、指摘だけを返してください。
```

参照：[Codex のスキル作成・配置に関する公式資料](https://learn.chatgpt.com/docs/build-skills)。
