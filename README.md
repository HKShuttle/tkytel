# 東京広域電話網そら局提供仕様書

sola-tel （通称：そら局）の提供仕様を示します。

相互接続のための情報は、東京広域電話網のDiscordから参照してください。

# PBX環境

- Rasberry Pi 4B 4GB + 256GB USB SSD
- [IchikawaYukko/docker-asterisk-letsencrypt: 20/11alpine3.22ja](https://github.com/IchikawaYukko/docker-asterisk_letsencrypt/tree/master)
  - アーキテクチャ違いのため、イメージはすべて自前でビルドしています
- Tailscale
- IPv4/IPv6 Dual Stack UDP/TCP
  - **TLS対応のサポートを終了しました**(Deprecated, no longer supported)。UDP/TCPで接続してください。
- mikopi.tail98edcb.ts.net (Tailscale内部のホスト名。 Aレコードが引けます)
  - 100.123.130.8
- mikotte.hk-shuttle.net (A/AAAA レコードが引けます)
  - 100.123.130.8
  - fd7a:115c:a1e0::3301:8208
 
## 接続方法

1. 東京広域電話網の折衝部「sola-tel (by HK_Shuttle)」スレッドのリンクより、Tailscaleに接続する
2. [いまさらVoIP網](https://zenn.dev/kusaremkn/articles/abd760f9f2f450) に従い、発信用設定、ルーティング設定を行う

- Provider host URL or IP address には、`mikotte.hk-shuttle.net` を設定するのがおすすめです。
  - IPv4/IPv6, UDP/TCPいずれの組み合わせも、このHostnameで接続できるように設定しています。

# mantela

<https://hkshuttle.github.io/tkytel/mantela.json>

# Preffered Prefix

- 944
- 0944

# 内線端末

- 3201
  - Linphone on Windows Mobile Laptop
  - 電源が入っているとき以外はオフラインです
- 3202
  - NTT ハウディ・クローバーホン S3 (via Yamaha RT58i)
  - 常時着信可能です（ただし不在にしている場合があります）
  - 平日および土休日の 19:00 - 23:30 ごろだと出られる可能性が高そうです
- 3203
  - Linphone on Sony Xperia 1 II (XQ-AT42)
  - バッテリー消耗防止のためほとんどオフラインです

いずれもそら本人に繋がります。

# テスト用番号

接続や死活の確認にいつでもご自由にご利用ください。

ちゃんとしたテスト用音声やBGMの追加はいつか暇な時にやります・・・。

- 3221
  - Read Back Service
- 3222
  - 1kHz Sine Wave
- 3223
  - Echo Back Service
