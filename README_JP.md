# v0.1.4, VRCSDK3-WORLD-2022.08.29.20.48_Public

  - VRCMirrorがカスタムカメラクリアフラグをサポートするようになったため、"TransparentBackground "マスクの必要性を削除しました。
  - このバージョンでは、VRCSDK3-WORLD-2022.08.29.20.48_Public またはそれ以降を使用していることを確認する必要があります。

# VRCPlayersOnlyMirror

素敵な地図で景色を眺めるか、自分の反射を見つめるかを選択するのにうんざりしていませんか？ 今、あなたは両方を同時に行うことができます！
VRCPlayersOnlyMirrorは、背景のないプレーヤーのみを表示するシンプルなミラーprefabです。
これは切り抜かれた2Dカメラではなく、完全な3Dミラーです。

  - 背景のない鏡でのプレイヤーの反射
  - 調整可能なミラーの透明度
  - 単純な距離フェード
  - PCとQuestの両方の世界で動作します
  - LQミラーとほぼ同等の性能コスト

# ダウンロード
  - [For SDK2 Worlds](https://github.com/acertainbluecat/VRCPlayersOnlyMirror/releases/download/v0.1.3/VRCPlayersOnlyMirrorSDK2_v0.1.3.unitypackage)
  - [For SDK3 Udon Worlds](https://github.com/acertainbluecat/VRCPlayersOnlyMirror/releases/download/v0.1.4/VRCPlayersOnlyMirrorSDK3_v0.1.4.unitypackage)

# 要件
  - VRChat SDK2 or SDK3
  - **!!! SDK3 VRCSDK3-WORLD-2022.08.29.20.48_Public または v0.1.4 用の新しいもの !!!**

# 方法

  - プロジェクトに応じて、SDK2またはSDK3のunitypackageをインポートします
  - サンプルシーンとprefabが提供されています

# シェーダの種類

  - **PlayersOnlyMirror** - 透明度と距離フェード付きの通常バージョン
  - **PlayersOnlyMirrorCutout** - カットアウトのみのバリエーションで、透明度や距離フェードはありません。

# シェーダー設定

  - **Base (RBG)** - デフォルトのミラーシェーダーと同じ動作で、テクスチャを反射にオーバーレイします 
  - **Hide Background** - 背景を非表示にします。これを機能させるには、ミラーの偽の背景として機能するTransparentBackgroundシェーダーが必要です。 
  - **Ignore Effects** - パーティクルやレンズフレアなどの効果を無視しようとします。ただし、キャラクターの前にいる場合は表示されます。
  - **Transparency** - ミラーの透明度を調整します 
  - **Transparency Mask** - ミラーの透明度を調整するテクスチャマスクは、完全に不透明な白から、黒で完全に透明になります。 SDK2のミラーマテリアルプロパティをアニメーション化できないため、主にSDK2のミラー全体の透明度をリアルタイムで調整するために使用されます。 詳細については、次のセクションを参照してください。 
  - **Distance Fade** - ミラーがゼロアルファにフェードし始めるまでの距離。 0で無効になります。 
  - **Distance Fade Length** - 距離フェード長-ゼロアルファにフェードするために必要な移動距離の長さ。 

# SDK2

  - ミラーが正しく機能するには「TransparentBackground」が必要ですが、VRCPlayersOnlyMirrorを使用していない他のミラーがシーンにある場合は、別のレイヤーに配置して、VRCPlayersOnlyMirrorのレイヤーにのみ表示することを検討してください。 それ以外の場合は、VRCPlayersOnlyMirrorもオンになっている場合は、フルミラーなど、他のミラーに表示されます。 必要に応じてサイズを変更します。
  - sdk2でミラーのマテリアルプロパティをアニメーション化することはできないため、カメラとレンダリングテクスチャは、UIスライダーを介してミラーの透明度を制御するために使用されます。
  - 複数のミラーがあり、独立した透明度スライダーが必要な場合は、個別のマテリアルを作成し、それぞれにテクスチャとカメラをレンダリングする必要があります。

# 欠点
  
  - ほとんどの透明な素材は鏡の中では不透明に見えます
  - 粒子、添加剤などは黒い輪郭になります
  - ミラーの後ろまたは前にある透明なマテリアルは、ミラーによって上書きまたは上書きされる可能性があります。レンダリングキューを調整すると、ステンシルを使用した最後の手段として役立ちます。

# Updates

#### 31st Aug 2022

  - VRCSDK3-WORLD-2022.08.29.20.48_Public では、VRCMirror でカスタム カメラ クリア フラグを設定できるため、「TransparentBackground」マスクは不要になりました。
  - SDK3のみ

#### 16th May 2021

  - シェーダーでToggleからToggleUIに変更し、使用するシェーダーキーワードを減らしました。

#### 6th Feb 2021

  - Cutoutバリアントを追加しました。このバージョンでは、ミラーの前後にある透過オブジェクトの問題は発生しないはずで、透過を必要としない場合に使用してください。  
  - 効果を無視するトグルを追加しました。パーティクル効果、レンズフレア、鏡面反射レンダリングテクスチャからゼロアルファとして読み込まれる特定の透明効果を無視しようとします。

# Demo

この鏡が実際に動いているのを見たい場合は、私の公開地図の一つ、Winter Solaceで見つけることができます。 
https://vrchat.com/home/world/wrld_8899947f-8e19-4981-b327-a63be233706a

![demo1](https://nyanpa.su/i/MKH21bPq.jpg)
![demo2](https://nyanpa.su/i/gEzZ1bQD.jpg)