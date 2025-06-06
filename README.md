# Discord OIDC Proxy
The proxy that enables applications using OpenID Connect (OIDC) authentication to authenticate users through Discord's OAuth2 system.

|       |        |
|-------|--------|
|English|[Japanese](./README-ja.md)|

Cloudflare Workers + Hono + pnpm

### What's this?

DiscordのOAuth2認証でOIDCログインできるようにするくん。

### Usage

1. `pnpx wrangler kv namespace create "AUTH_KV"`を実行してKVを作成する
2. 出てきたIDで`wrangler.jsonc`の`<YOUR_KV_NAMESPACE_ID>`を置換する。
3. 一度`pnpm install && pnpm release`する
4. 出てきたデプロイ先Url(`https://hoge.workers.dev`)で`wrangler.jsonc`の`https://<YOUR_WORKERS>.workers.dev`を置換する
5. OIDCを使うアプリにクライアントIDがあれば`<OIDC_AUDIENCE>`を置換する。
6. [Discord Developer Portal](https://discord.com/developers/applications)でApplicationを作成する
7. OAuth2のClient IDとClient Secretを控える
8. `setup.sh`を実行し、指示に従ってClient IDとClient Secretを入力する
9. `pnpm release`して完成
