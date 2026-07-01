# tagpr-monorepo-sample

[tagpr](https://github.com/Songmu/tagpr) のモノレポ対応サンプルリポジトリです。

## Structure

ディレクトリ単位でリリース対象が存在し、それぞれ独立したバージョニングを行います。

| Directory | Tag Format | Description |
|-----------|------------|-------------|
| `targetA/` | `targetA/vx.y.z` | リリース対象 A |
| `targetB/` | `targetB/vx.y.z` | リリース対象 B |

## How it works

1. `main` ブランチへの push 時に、変更されたディレクトリを検知
2. 変更のあったターゲットに対してのみ tagpr を実行
3. tagpr がリリース用の Pull Request を作成し、マージ時にタグを付与

各ディレクトリの `.tagpr` で `tagPrefix` を設定することで、`targetA/v0.1.0` のようなプレフィックス付きタグが生成されます。
