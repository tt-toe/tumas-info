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
   1. Up (アップ)
      - 場に出すカードをHand(手札)から選択する
   1. Down (ダウン)
      - Upしたカードの選択を取り止める
   1. Play (プレイ)
      - 選択したカードを場に出す
   1. Draw (ドロー)
      - ターン最初にDeckからカードを取ること
   1. Shuffle (シャッフル)
      - Deckが空になった場合、Discard Pileから順番をランダムに並べ直したカードをDeckへ戻すこと

1. Game Phase
   下記の繰り返しでゲームを進めていく
   1. Plan Phase
      - カードをDrawし、その中から複数枚をUpすることで1ターンあたりで行うことを決める
   2. Action Phase
      - Upしたカードに応じた効果が発動する
   3. Scenario Phase
      - Actionの効果および他の状況から追加の効果が発動、シナリオ上の選択やリソース管理を行う
      
1. User / Player State
   1. アカウント作成
      - OAuthまたはE-mail認証
   3. プロフィール作成
      - Player単位の生成
   5. ジョブ選択
      - 初期Tuberおよび初期カードの生成
