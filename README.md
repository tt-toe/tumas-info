# tumas-info
1. Terminology
   1. Card (カード)
      - Deck、Hand、Discard Pileに含まれるカード
   1. Deck (山札)
      - チャンネル(Channel)の役割(Role)毎が持つ山札
   1. Hand (手札)
      - チャンネル(Channel)の役割(Role)毎が持つ手札
   1. Discard Pile (墓場)
      - 捨て札(の山)。
   1. Play (プレイ)
      - 選択したカードを場に出す
   1. Draw (ドロー)
      - ターン最初にDeckからカードを取ること
   1. Shuffle (シャッフル)
      - Deckが空になった場合、Discard Pileから順番をランダムに並べ直したカードをDeckへ戻すこと
   1. Up (アップ)
      - 提示されたカードから選択する
   1. Down (ダウン)
      - Upしたカードの選択を取り止める

1. Game Phase
   * 下記の繰り返しでゲームを進めていく
   1. Plan Phase
      - カードをDrawし、その中から任意のカードをPlayし1ターンあたりで行うことを決める
   2. Action Phase
      - Playしたカードに応じた効果が発動する
   3. Scenario Phase
      - Actionの効果および他の状況から追加の効果が発動、シナリオ上の選択やリソース管理を行う
      
1. User / Player State
   1. アカウント作成
      - OAuthまたはE-mail認証
   2. プロフィール作成
      - Player単位の生成
   3. ジョブ選択
      - 初期Tuberおよび初期カードの生成

1. 各Phaseのメカニズム
   1. Plan Phase
      1. Tuber毎に設定されたDraw枚数を各TuberのDeckからDrawしてHandとする
      1. 各TuberのHandからカードを選択させ、Chの残エナジー >= 選択したカードのコスト の場合、選択したカードをPlayする
         1. Playしたカードの効果は下記に大分類される
            * 単効果
               カードの特徴に応じてゲーム内要素に影響を与える(ex. Tuberのステータス変化、Siteからの情報入手、Channelの状態変化)
            * 複合効果
               Play後、新たに単数または複数のカードをUpする。Upに応じてゲーム内要素に影響を与える(ex. Video投稿、カード削除、カードアップグレード、機材購入)
               Handから選択させる場合、Chの残エナジー > 選択したカード の条件が成立するカードのみUp可
      1. 単効果の場合、Play毎に状態が反映される
         複合効果の場合、選択対象のカードをプレイヤーへ提示する画面へ遷移し、適宜Up/Downを要求する
      1. PlayできるカードがなくなるとNext Phaseへの移行を示唆する
   1. Action Phaseのメカニズム
      1. Planの実行結果に応じた処理が行われる
   1. Scenario Phaseのメカニズム
      1. Actionの結果に応じて次のScenarioが提示される
