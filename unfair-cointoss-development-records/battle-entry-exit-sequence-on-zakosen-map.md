# 雑魚出現マップでの戦闘入出シーケンス

2024-12-05  

* 📺 [雑魚戦に入る前](https://x.com/muzudho1/status/1864657829640245301)
* 📺 [雑魚戦が終わったとき](https://x.com/muzudho1/status/1864658469640450398)


## 戦闘前の歩行マップ

2024-12-13 22:38  

雑魚が２匹、イベントマスターが１つある  


```plaintext
3 イベントマスター　＞　雑魚戦
5: ♠開始　＆　手動設定


コモンイベント［データ読込　＞　雑魚戦マップ読込時、各雑魚毎］
デバッグルーム　雑魚戦部屋
1 真心をお届けする八百屋　木村
1: イベントシート
-
♧場所　＞　戦闘者ゲームオブジェクトＩｄ：通し（１～）：
    `4`
♧場所　＞　戦闘者ゲームオブジェクト番号ｎ：マップ内（１～）：
    `1`


デバッグルーム　雑魚戦部屋
1 真心をお届けする八百屋　木村
6: ♠（定型処理）開始
-
戦闘者ゲームオブジェクトＩｄ：通し（１～）：
    `4`
戦闘者ゲームオブジェクト番号ｎ：マップ内（１～）：
    `1`


コモンイベント［データ読込　＞　雑魚戦マップ読込時、各雑魚毎］
デバッグルーム　雑魚戦部屋
2 歌って踊れる美容師　中野
1: イベントシート
-
♧場所　＞　戦闘者ゲームオブジェクトＩｄ：通し（１～）：
    `5`
♧場所　＞　戦闘者ゲームオブジェクト番号ｎ：マップ内（１～）：
    `2`


デバッグルーム　雑魚戦部屋
2 歌って踊れる美容師　中野
6: ♠（定型処理）開始
-
戦闘者ゲームオブジェクトＩｄ：通し（１～）：
    `5`
戦闘者ゲームオブジェクト番号ｎ：マップ内（１～）：
    `2`


※逐次処理終了


デバッグルーム　雑魚戦部屋
1 真心をお届けする八百屋　木村
1: （定型処理）急接近～遭遇


コモンイベント［雑魚戦　＞　急接近～遭遇］
わらべ島西　チクザイ海岸（または　デバッグルーム　雑魚戦部屋）
1 真心をお届けする八百屋　木村
-
1: イベントシート
-
戦闘．設定　＞　戦闘者ゲームオブジェクトＩｄ：通し（１～）：
    `4`     ※ ここに必ず１以上の数が入っている必要があります
場所　＞　雑魚ｎの長い名前[4]:
    ``
戦闘．設定　＞　%Bob戦闘者%の長い名前:
    `真心をお届けする八百屋　木村`  ※ ここに必ず設定されている必要があります
♧場所　＞　戦闘者ゲームオブジェクトＩｄ：通し（１～）：
    `4`


コモンイベント［データ読込　＞　戦闘入前］
デバッグルーム　雑魚戦部屋
1 真心をお届けする八百屋　木村
-
1: データ取出し
-
戦闘．設定　＞　%Bob戦闘者%の長い名前：
    `真心をお届けする八百屋　木村`


1 真心をお届けする八百屋　木村
4: （定型処理）雑魚位置記憶


2 謳って踊れる美容師　中野
4: （定型処理）雑魚位置記憶


3 イベントマスター　＞　雑魚戦
4: 戦闘入前　＞　雑魚位置記憶指示終了


3 イベントマスター　＞　雑魚戦
3: 戦闘入前　＞　雑魚戦に入る前に準備する


※ ここで戦闘マップへ突入
```


## 戦闘マップ

```plaintext
このイベント名＝イベントマスター
イベントシーン名＝1: ♠戦闘入後　＞　戦闘マップに入っている


※「～が現れた！」「どちらを選ぶ？」「ｳﾗ」


このイベント名＝コイン
イベントシート名＝１：戦闘中　＞　コインが投げられて落ちるまで


※「表が出た」


このイベント名＝Bob戦闘者
イベントシート名＝4: 戦闘Bob　＞　「当たった」


※　「やったぜ！　当たった！」


このイベント名＝Alice戦闘者
イベントシート名＝3: 戦闘Alice　＞　「ハズレかあ」


※　「ハズレかあ」
※　「木村に勝ち点１が入って　合計１点だ」


このイベントシート名＝Bob戦闘者
イベントシート名＝2: 戦闘Bob　＞　優勝を宣言する


※　「１点取ったから、わたしの優勝だな」
※　フェードアウト


3 イベントマスター　＞　雑魚戦
2: 戦闘出後　＞　雑魚位置を復元する


1 真心をお届けする八百屋　木村
5: （定型処理）雑魚位置復元


2 謳って踊れる美容師　中野
5: （定型処理）雑魚位置復元


3 イベントマスター　＞　雑魚戦
1: 戦闘出後　＞　このマップへフェードインする
```


## 戦闘後の歩行マップ

```plaintext
※　フェードインする。「～を手放した！」


2 歌って踊れる美容師　中野
2: （定型処理）しばらく雑魚戦が起こらない


※　これで終わり
```

