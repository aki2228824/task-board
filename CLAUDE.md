# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Git 運用ルール

コードを変更するたびに、以下の手順で GitHub にプッシュすること：

1. 変更内容を確認する: `git diff`
2. 変更をステージング: `git add <files>`
3. コミット: `git commit -m "<変更内容を簡潔に説明するメッセージ>"`
4. プッシュ: `git push origin <branch>`

- コミットメッセージは変更の「なぜ」を中心に書く
- プッシュは毎回の変更ごとに行い、ローカルにコミットを溜め込まない
- `git push --force` は原則禁止（ユーザーが明示的に指示した場合のみ実行）
