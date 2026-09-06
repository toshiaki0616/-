# Legacy Mixed Repository

> Status: **ARCHIVE CANDIDATE**

このRepositoryは、過去のVBA断片とGoogle Colab Notebookが混在した旧作業置き場です。現在の開発正本としては使用しません。

## Canonical destinations

### VBA

本Repositoryに残るVBA 4本は、用途確認・安全化・レビュー後に `toshiaki0616/VBA-Catalog` へ正本化済みです。

| Legacy asset | 現在の扱い |
|---|---|
| `VBA：エクセルファイルを1つに集約` | `VBA-Catalog/vba/excel/merge_workbooks_to_new_book.bas` が正本 |
| `フォルダからフォルダへ特定の当てはまるキーワードのファイルを移動` | `VBA-Catalog/vba/file_operations/move_files_by_keyword_safe.bas` が安全版正本 |
| `文字を置換 置換後、背景色を薄赤色に変換` | 旧ファイル名と実体が不一致。`VBA-Catalog/vba/excel/highlight_matching_text_safe.bas` が整理済み正本 |
| `特定の名前があるファイルを削除 ※ゴミ箱に行かないため取り扱い注意` | 破壊的legacyとして `VBA-Catalog/projects_archive/vba_collection/delete_files_by_keyword_unsafe_legacy.bas` に隔離 |

本Repository側の旧VBAを実運用へ戻さないでください。

## Legacy notebooks

### `whisper_mock_en.ipynb`

Google Colab向けのWhisper文字起こし試作です。

- `openai/whisper` をGitHubからinstall
- Whisper `base` modelを使用
- 日本語 / 英語を選択
- 文字起こし結果をtxtへ保存
- 出力フォルダをzip化してdownload

単体実験としては成立していますが、現行アプリの正本ではありません。歴史的なPrototypeとして本Repository内に保持します。

### `スクレイピング.ipynb`

Selenium + Chromiumを使った古いColab試作です。

確認済みの問題:

- 保存済み実行結果に `ModuleNotFoundError: No module named 'selenium'`
- `find_element_by_class_name` / `find_element_by_tag_name` 等の旧Selenium APIを使用
- コードセル内に生の `【結果】` があり、そのままでは有効なPythonコードではない
- 特定サイトの表取得だけを試した小規模実験

現在の再利用対象ではなく、**Legacy / Broken experiment** としてのみ保持します。

## Repository policy

- 新規開発はここで行わない
- VBAは `VBA-Catalog` を正本とする
- Notebookを再利用する場合は、新しい目的のRepositoryまたはIssueから作り直す
- 本Repositoryの内容は削除せず、履歴確認用に保持する
- Repository本体はGitHub管理画面でArchive候補とする

Related: Issue #1
