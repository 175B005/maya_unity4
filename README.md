# maya_unity4
maya unity 連携機能４（アニメーション　リグ・クリーチャアニメ編）

### まだです。

1. 今回はまず、[前回の手順]()を元に、自分の作ったモデルにアニメーションをつけていきたいと思います。
1. 人型であれば、humanoidが使えるので、クイックリグでポイッとできてしまうので、  
前回のようにすぐできるのですが、今回はジョイントの設定から、ひとつずつやっていきます。
1. こんなモデルを作りました。[LOBOTERモデルデータ](https://github.com/175B005/maya_unity4/raw/master/directionf.zip)  
（作り方は[次のページ]()で紹介しています。）   
モデル、色付け、完成版（リギング済）、をzipファイルにてアップしてます。どうぞお使いください。↑
1. 前回と同様にリグをつけていきます。今回は一から作っていくので、クイックリグは使用しません。
1. まずジョイントを作成していきます。連携 機能５で作成、説明してあります、モデルを使っていきます。  
リギングメニュー上部< スケルトン< ジョイントの作成→ジョイントツール  
or　リギングショートカット< 関節のマーク　でも可  
ツール状態になったら、ｸﾘｯｸをすると、した場所にジョイントが追加されます。  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction8-3.jpg)
1. 再度ツールを選択して、クリック！→　どんどん作っていきます。  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction9-3.jpg)
1. Ctrl + Dでコピーできます。複製して関節と先端にジョイントをつけます。  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction10-3.jpg)
1. 次は、接続していきましょう。  
子したいジョイント→親になるジョイントの順に選択。　スケルトン< ジョイントの接続　  
から接続メニューを出し、「親ジョイント」の方を選択。  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction11-3.jpg)
1. 親ジョイント：親子関係を作ります。
1. ジョイントの接続：兄弟関係を作ります。  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionj.jpg)
1. 足部分を作って、、、（ジョイントにもしっかり名前をつけています。（左）  
※アウトライナでみると、親子になっているのがはっきりとわかります。。）  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction13-3.jpg)
1. 最後に、全てをBodyの子にして行きます。  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction14-3.jpg)
1. スキンをバインドをします。まず、オブジェクト全選択。  
（アウトライナから選択するほうが、正確にできると思います。）  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction15-3.jpg)
1. Shift 押しながら、さっきつけたリグも選択。  
上部メニュー< スキン< スキンのバインド　からバインドをかけます。(これでモデルとリグがくっつきました。)  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction16-3.jpg)
1. ですが、このまま動かすといらないものまで動いてしまうので、調整します。
1. スキン< スキンのウェイトペイント　を選択。  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction17-3.jpg)
1. ペイントのメニューは枠線上から、ジョイントの詳細。ツールのモード。  
ペイントの筆の強さ。カラーの欄は、見やすくするための色です。（赤にしてます。）  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction18-3.jpg)
1. 初めに初期化しておきます。　スキン< 既定のウェイトをリセット  
これで、自動でついていた、ウェイトがリセットされました。（ある程度残りますが、稼動部なので、消せないです。）  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction23-3.jpg)
1. ペイントしていきましょう。  
ペイントするジョイントを選択。さっきのツールモードから、ペイントを選択。  
稼動させる場所。（そのジョイントの付近）  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction19-3.jpg)
1. 第二ジョイント（関節）  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction20-3.jpg)
1. 第三ジョイント（先端）  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction21-3.jpg)
1. Shiftを押しながら「ペイント」すると、「SM」と出るので、その状態は、マイナスのペイント（削除）になる。  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction24-3.jpg)
1. 完成でーす。  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction25-3.jpg)

---

1. ではアニメをつけていきましょう。手順は前回と同じ！  
下のフレームを 1 に設定したら、初期のアニメをまず登録。キーの値を設定します。  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction26-3.jpg)
1. 次に設定したいフレームを選択、キー値設定。（間は自動で動いてくれる。）  
※ここで注意しておきたいのは、前回と違って、「コントロールリグ」ではないので、  
　 下位層のジョイントを動かしても、親が回転しないってコトです（関節の稼動域の問題で）。  
 　関節は反対には曲がりませんよね、、ひゃー怖い。。  
   物理的に動かせないので、全部作っていく必要があります。。  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/direction27-3.jpg)

---

1. 今回のボーン(リグ)はHumanoidでは無いので、Genericにしておきます。(前回参照)  
![](https://raw.githubusercontent.com/175B005/maya_unity3/master/directionx18.jpg)
1. 前回ページを参考に、unity側でアニメーションを設定できたら、さあ動かして見ましょう。

 [前ページ](https://github.com/175B005/maya_unity3a)| [次ページ](https://github.com/175B005/maya_unity5)|[目次](https://github.com/175B005/maya_unity_index)
