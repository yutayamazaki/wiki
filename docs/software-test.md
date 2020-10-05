# ソフトウェアのテスト

## 概要

ソフトウェアの動作の正しさを確かめるために，各関数のユニットテストから人手で画面を操作するものまで，様々なテストが行われる．本記事では人手でない自動テストについて主に記載する．

## テストの役割

ソフトウェアのテストにはいくつかの役割がある．

- 実装の正しさを保証する
  - テストケースが正しく通ることでその実装が適切であることが把握できる
- 開発速度を早める
  - コードに変更を加える場合に，以前のテストと同じ結果を出力しているのであれば変更が適切であることが確認できる
  - 新たな変更によってコードが壊れていないことが分かるため，コードを変更することを躊躇わなくなる
- コードの品質を高く保つ
  - ユニットテストが書きにくいコードは既に汚いコードであることが多い
  - テストを念頭にコードを書くことで，テストのしやすい可読性の高いコードが書ける
- バグを潰す
  - 一度発生したバグをテストケースとして追加することで，そのバグが再現することを防ぐことができる

実装の正しさ・コードの品質を高め，開発速度を上げていきたい場合はユニットテストや統合テスト，ユーザーがバグを体験する機会を減らしたい場合はUIテストなどのようにテスト毎に役割・目的が異なる．そのためどの目的でテストを行うかを事前にチームで確認する必要がある．


## 自動テストのピラミッド

自動テストにはそのカバーする範囲から大きく3つの種類に分類される．

- UIテスト
  - UIを介してシステムをE2Eでテストする
  - 実際にユーザーがシステムを利用する場合と同様の動きを自動で実行する
  - ユニットテストや統合テストと比較して実行時間が長く，またメンテナンスのコストも大きいため書かれないことも多い
- 統合テスト
  - UIを返さずにAPIなどのロジックをテストする
  - ユニットテストと比較して厳密にどの箇所が壊れているのかはわからないが，コードの統合に問題がないかを確認できる
  - メンテナンスのコストはユニットテストとそう変わらない
- ユニットテスト
  - 高速に動作し，壊れている箇所を正確に把握することができる
  - メンテナンスのコストが低い

[Google Testing Blog: Test Sizes](https://testing.googleblog.com/2010/12/test-sizes.html)によると，GoogleではUIテスト・統合テスト・ユニットテストという分類ではなく，データの通信や外部システムの依存関係，実行時間などに応じてSmall, Medium, Largeのように種類を区分している．UIテスト・統合テスト・ユニットテストは厳密な区分があるわけではないので，より厳密にテストを呼び分けてメンバー間の連携を取りやすくするという目的があるらしい．


## テスト関連のおすすめ記事・書籍

- [テスト自動化 / Test_Automation - Speaker Deck](https://speakerdeck.com/cybozuinsideout/test-automation)
- [Google Testing Blog](https://testing.googleblog.com/)
- [Google Testing Blog: Test Sizes](https://testing.googleblog.com/2010/12/test-sizes.html)
- [組織にテストを書く文化を根付かせる戦略と戦術](https://www.slideshare.net/t_wada/test-strategy-and-tactics)
  - @t_wada によるテストに対する考え方が知れるスライド
- [初めての自動テスト](https://www.oreilly.co.jp/books/9784873118161/)
  - テストの概要・区分・目的などを記載しており，体系的に自動テストについて学ぶことができる