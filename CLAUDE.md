# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## プロジェクト概要

このリポジトリは日本の技術ブログプラットフォーム「Zenn」用のコンテンツ管理リポジトリです。技術記事と書籍のMarkdownファイルを管理し、Zenn CLIを使用してローカルプレビューや新規コンテンツの作成を行います。

## 主要コマンド

### 開発環境セットアップ

```bash
pnpm install  # 依存関係のインストール
```

### コンテンツ管理

```bash
pnpm preview      # ローカルプレビューサーバー起動（http://localhost:8000）
pnpm new:article  # 新しい記事の作成
pnpm new:book     # 新しい書籍の作成
```

### コード品質

```bash
pnpm lint    # Markdownファイルのlinting（articles/とbooks/が対象）
pnpm format  # Markdownファイルの自動修正
```

## アーキテクチャ

### ディレクトリ構造

- `articles/` - 技術記事のMarkdownファイル（ファイル名は自動生成されるID）
- `books/` - 書籍コンテンツのディレクトリ
- `images/` - 記事内で使用する画像ファイル

### Zenn記事のフロントマター構造

```yaml
---
title: "記事タイトル"
emoji: "😊"
type: "tech"  # tech: 技術記事 / idea: アイデア
topics: ['javascript', 'react']  # タグ（最大5個）
published: true  # true: 公開済み / false: 下書き
---
```

## 設定・ツール

### パッケージマネージャー

- **pnpm**を使用

### Markdownlinting

- `markdownlint-cli2`を使用
- 設定ファイル: `.markdownlint-cli2.yaml`

## 重要な注意事項

- 新規の記事や書籍を作成する際は必ず `pnpm new:article` または `pnpm new:book` を使用すること
- 記事ファイル名は変更しないこと（ZennのURLに影響する）
- 画像は`images/`ディレクトリに配置し、相対パスで参照する
- publishedをtrueにすると即座にZennで公開される
