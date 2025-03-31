# 問題生成アプリケーション

このアプリケーションは、テキストや画像から問題を自動生成するWebアプリケーションです。Streamlitを使用して構築されており、多言語対応とAIを活用した問題生成機能を提供します。

## 主な機能

- 📝 問題生成
  - テキストベースの問題生成
  - 画像からのテキスト抽出と問題生成
  - カメラを使用したリアルタイム画像キャプチャ
- 🌐 多言語対応
  - 韓国語
  - 英語
  - 日本語
  - 中国語
  - ミャンマー語
- 🎯 カスタマイズ可能な問題設定
  - 問題数
  - 問題タイプ（選択式、穴埋め、記述式）
  - 難易度
  - トピック
  - 回答形式
- 💾 データベース連携
  - 生成された問題と回答の保存
  - 履歴管理

## 必要条件

- Python 3.10以上
- MySQLデータベース
- OpenAI APIキー
- Google Cloud Vision APIキー

## セットアップ方法

1. リポジトリのクローン
```bash
git clone [repository-url]
cd [repository-name]
```

2. 仮想環境の作成と有効化
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
```

3. 必要なパッケージのインストール
```bash
pip install -r requirements.txt
```

4. データベースのセットアップ
- MySQLデータベースを作成
- 以下のテーブルを作成：
```sql
CREATE TABLE moning (
    id INT AUTO_INCREMENT PRIMARY KEY,
    Quiz_text TEXT,
    Quiz_trans TEXT,
    Quiz_qust TEXT,
    Quiz_ans TEXT
);
```

5. 環境変数の設定
- OpenAI APIキーを設定
- Google Cloud Vision APIキーを設定

## 使用方法

1. アプリケーションの起動
```bash
streamlit run Generator.py
```

2. ブラウザで http://localhost:8501 にアクセス

3. サイドバーから機能を選択：
   - 📝問題 만들기：問題生成
   - 📄📱🎨Demo Page：デモページ
   - Code Page：コード表示

## プロジェクト構造

```
.
├── Generator.py      # メインアプリケーションファイル
├── page1.py         # 問題生成ページ
├── page2.py         # デモページ
├── page3.py         # コード表示ページ
├── requirements.txt # 依存パッケージリスト
└── README.md        # このファイル
```

## 注意事項

- APIキーは適切に管理し、公開しないようにしてください
- データベースの接続情報は環境に合わせて設定してください
- 画像処理機能を使用する場合は、カメラへのアクセス権限が必要です

## ライセンス

このプロジェクトはMITライセンスの下で公開されています。 