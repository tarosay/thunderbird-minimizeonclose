# Minimize on Close add-on for Thunderbird

An add-on to minimize Thunderbird when clicking on the close button. You can [download stable releases through addons.thunderbird.net](https://addons.thunderbird.net/thunderbird/addon/minimize-on-close/). Alternatively, binary builds for named versions are also available [on the releases page of this repository](https://github.com/rsjtdrjgfuzkfg/thunderbird-minimizeonclose/releases).


## Compatibility

**This add-on officially supports the Extended Support Release (ESR) channel of Thunderbird.** For a seamless and stable user experience, compatibility updates are planned to land before each major ESR release. If you use the ESR release channel and have automatic updates enabled, Thunderbird will ensure that a compatible version is installed at any time.

All other channels, including the new monthly "release" channel, do not receive official support. That said, pull requests that provide compatibility fixes for other versions are welcome, if they do not interfere with ESR releases.

To protect you and your data, regular releases of the add-on cannot be enabled on unsupported versions of Thunderbird. Advanced users that understand the risks involved may use unsupported builds that can be installed on newer versions of Thunderbird. As the name implies, unsupported builds do not receive any form of support from the add-on author and are not published as automatic updates. Do not open issues or otherwise ask the add-on author for support when using an unsupported build.

Beware: While unsupported builds may seemingly work as intended, incompatible changes in Thunderbird might affect some or all functionality of the add-on and may lead to severe issues, even beyond the add-on's scope. In extreme cases, using unsupported builds could lead to irrecoverable loss of data. If you do not understand the risks involved, don't have a tested and relieable backup strategy, or don't want the hassle of updating the add-on manually, you should use supported releases with an ESR version of Thunderbird.


## Building

On a system with common unix tools installed, you can use `make` to create an xpi archive containing the add-on in the dist folder. For an unsupported build, use `make xpi-unsupported` instead.

Alternatively, you can directly use the add-on from the `src` folder or pack that folder into an xpi yourself.

# Thunderbird用 Minimize on Close アドオン

閉じるボタンをクリックした際に、Thunderbirdを最小化するためのアドオンです。[addons.thunderbird.net から安定版リリースをダウンロード](https://addons.thunderbird.net/thunderbird/addon/minimize-on-close/)できます。また、特定のバージョン向けのバイナリビルドは、[このリポジトリのリリースぺージ](https://github.com/rsjtdrjgfuzkfg/thunderbird-minimizeonclose/releases)からも入手可能です。

## 互換性

**このアドオンは、Thunderbirdの延長サポート版（ESR）チャンネルを公式にサポートしています。** シームレスで安定したユーザー体験を提供するため、互換性アップデートは主要なESRリリースの前に適用されるよう計画されています。ESRリリースチャンネルを使用し、自動更新を有効にしている場合、Thunderbirdは常に互換性のあるバージョンがインストールされている状態を保ちます。

新しい月次「リリース」チャンネルを含む、他のすべてのチャンネルは公式サポートの対象外です。ただし、ESRリリースに支障をきたさない範囲であれば、他のバージョンへの互換性修正を提供するプルリクエストは歓迎します。

ユーザーとそのデータを保護するため、Thunderbirdの非サポートバージョンでは、このアドオンの通常リリースを有効にすることはできません。リスクを理解している上級ユーザーであれば、新しいバージョンのThunderbirdにインストール可能な「非サポートビルド」を使用することができます。その名の通り、非サポートビルドはアドオン作者からのいかなるサポートも受けられず、自動更新として公開されることもありません。非サポートビルドを使用する際は、Issueを開いたり、アドオン作者にサポートを求めたりしないでください。

**注意：** 非サポートビルドは一見意図した通りに動作するように見えるかもしれませんが、Thunderbird側の互換性のない変更により、アドオンの一部の機能、あるいは全機能に影響が及ぶ可能性があり、アドオンの範囲を超えた深刻な問題を引き起こす恐れがあります。極端なケースでは、非サポートビルドの使用が回復不能なデータの損失につながる可能性もあります。リスクを理解していない場合、テスト済みの信頼できるバックアップ戦略がない場合、またはアドオンを手動で更新する手間をかけたくない場合は、ESR版のThunderbirdでサポートされているリリースを使用すべきです。

## ビルド

一般的なUnixツールがインストールされているシステムでは、`make` コマンドを使用して、distフォルダ内にアドオンを含むxpiアーカイブを作成できます。非サポートビルドを作成する場合は、代わりに `make xpi-unsupported` を使用してください。

あるいは、`src` フォルダから直接アドオンを使用するか、そのフォルダをご自身でxpiにパックして使用することも可能です。

## ソースコードからの手動インストール

`src` フォルダと中身がお手元にある場合、以下の手順でThunderbirdに導入できます。

### 方法1：.xpi ファイルを作成してインストールする（推奨）

通常利用する場合は、以下の手順でインストール可能なパッケージファイルを作成してください。

1.  **圧縮する**
    `src` フォルダの**中に入り**、すべてのファイル（`manifest.json` 等）を選択してZIP形式に圧縮します。
    * *注意: `src` フォルダそのものを圧縮するのではなく、フォルダ内のファイル群をルートとして圧縮してください。*
2.  **拡張子を変更する**
    作成したZIPファイルの拡張子 `.zip` を `.xpi` に変更します。（例: `my-addon.xpi`）
3.  **インストールする**
    Thunderbirdを開き、右上のメニュー（≡）から **「アドオンとテーマ」** を開きます。歯車アイコン（⚙️）をクリックし、**「ファイルからアドオンをインストール」** を選択して、作成した `.xpi` ファイルを読み込みます。

### 方法2：一時的なアドオンとして読み込む（開発・テスト用）

ファイルを圧縮せず、直接読み込ませて動作確認を行う方法です。

1.  Thunderbirdを開き、右上のメニュー（≡）から **「アドオンとテーマ」** を開きます。
2.  歯車アイコン（⚙️）をクリックし、**「アドオンをデバッグ」** を選択します。
3.  表示された画面の **「一時的なアドオンを読み込む... (Load Temporary Add-on...)」** ボタンをクリックします。
4.  `src` フォルダの中にある `manifest.json` ファイルを選択して「開く」をクリックします。

* *注意: この方法でインストールしたアドオンは、Thunderbirdを再起動すると削除される場合があります。*