# 東京広域電話網そら局提供仕様書

sola-tel （通称：そら局）の提供仕様を示します。

相互接続のための情報は、東京広域電話網のDiscordから参照してください。

# PBX環境

- Rasberry Pi 4B 4GB + 256GB USB SSD
- [IchikawaYukko/docker-asterisk-letsencrypt: 20/11alpine3.22ja](https://github.com/IchikawaYukko/docker-asterisk_letsencrypt/tree/master)
  - アーキテクチャ違いのため、イメージはすべて自前でビルドしています
- Tailscale
- IPv4/IPv6 Dual Stack UDP/TCP/TLS
- mikopi.tail98edcb.ts.net (Tailscale hostname, A Record is set)
  - 100.123.130.8
- mikotte.hk-shuttle.net (for TLS Domain Validation, A/AAAA Record is set)
  - 100.123.130.8
  - fd7a:115c:a1e0::3301:8208

# mantela

https://hkshuttle.github.io/tkytel/mantela.json

# Preffered Prefix

- 944
- 0944

# 内線端末

- 3201
  - Linphone on Windows Mobile Laptop
  - 電源が入っているとき以外はオフラインです
- 3202
  - NTT 600-A2 Classic Style Dial Phone, Connected via Yamaha RT58i
  - 常時オンラインです
  - 平日および土休日の 19:00 - 23:30 ごろだと出られる可能性が高そうです
- 3203
  - Linphone on Sony Xperia 1 II (XQ-AT42)
  - バッテリー消耗防止のためほとんどオフラインです

いずれもそら本人に繋がります。

（まずないと思いますが）実家に設置しているため、うっかり家族が出てしまった場合は悪しからず。

発信はいつでも構いませんが、可能なら事前にコンタクトいただけるととてもスムーズに対応できると思います🙂

# テスト用番号

接続や死活の確認にいつでもご自由にご利用ください。

- 3221
  - Read Back Service
- 3222
  - 1kHz Sine Wave
- 3223
  - Echo Back Service
