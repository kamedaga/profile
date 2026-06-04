# Profile Site

プロフィールサイト

## Commands

```sh
deno task dev
deno task build
deno task preview
```

## Deno Deploy

このサイトは Vite が生成する `dist` を Deno Deploy の Static mode で配信します。

初回だけアプリを作成します。

```sh
deno task deploy:create
```

対話で organization / app name などを選んだあと、以降は次で production deploy できます。

```sh
deno task deploy
```

GitHub 連携で設定する場合は以下にします。

- Runtime mode: `static`
- Build command: `deno task build`
- Static directory: `dist`
- Single Page App mode: enabled
