# 🤖 Setup GitHub App as bot

Generate a [GitHub App](https://docs.github.com/apps) access token and set up bot git identity for CI workflows.

## Usage

See [action.yml](https://github.com/SimonMarquis/setup-github-app-as-bot/blob/main/action.yml)

```yml
steps:
  - uses: SimonMarquis/setup-github-app-as-bot@v1
    with:
      client-id: ${{ secrets.APP_CLIENT_ID }}
      private-key: ${{ secrets.APP_PRIVATE_KEY }}
```

| Input                | Description                                                      |
|----------------------|------------------------------------------------------------------|
| `client-id`          | GitHub App client ID.                                            |
| `private-key`        | GitHub App private key.                                          |
| `gh-auth-login`      | When `true` (default), run `gh auth login` with the app token.   |
| `set-git-user`       | When `true` (default), configure the global git user as the bot. |

| Output           | Description                                                               |
|------------------|---------------------------------------------------------------------------|
| `app-slug`       | GitHub App slug                                                           |
| `token`          | GitHub App installation access token                                      |
| `user-id`        | GitHub App user id                                                        |
| `git-user-name`  | Git user name                                                             |
| `git-user-email` | Git email address                                                         |
| `git-identity`   | Git identity (e.g. `my-bot <12345+my-bot[bot]@users.noreply.github.com>`) |
