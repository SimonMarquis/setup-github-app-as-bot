# 🤖 Setup GitHub App as bot

Generate a [GitHub App](https://docs.github.com/apps) access token with [`actions/create-github-app-token`](https://github.com/actions/create-github-app-token) and set up bot git identity for CI workflows.

## Usage

See [action.yml](https://github.com/SimonMarquis/setup-github-app-as-bot/blob/main/action.yml)

```yml
steps:
  - uses: SimonMarquis/setup-github-app-as-bot@v1
    with:
      client-id: ${{ secrets.APP_CLIENT_ID }}
      private-key: ${{ secrets.APP_PRIVATE_KEY }}
```

| Input               | Description                                                                                                                                                          |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `client-id`         | GitHub App client ID.                                                                                                                                                |
| `private-key`       | GitHub App private key.                                                                                                                                              |
| `gh-auth-login`     | When `true` (default), authenticate GitHub CLI (`gh`) using the generated GitHub App token.                                                                          |
| `gh-auth-setup-git` | When `true` (default), configure Git to use GitHub CLI (`gh`) as its credential helper for GitHub hosts.                                                             |
| `set-git-user`      | When `true` (default), configure the global git user as the bot.                                                                                                     |
| `permission-*`      | Grant the token a permission level (`read`, `write`, etc.) as described in [`actions/create-github-app-token`](https://github.com/actions/create-github-app-token)   |

| Output           | Description                                                               |
|------------------|---------------------------------------------------------------------------|
| `app-slug`       | GitHub App slug                                                           |
| `token`          | GitHub App installation access token                                      |
| `user-id`        | GitHub App user id                                                        |
| `git-user-name`  | Git user name                                                             |
| `git-user-email` | Git email address                                                         |
| `git-identity`   | Git identity (e.g. `my-bot <12345+my-bot[bot]@users.noreply.github.com>`) |
