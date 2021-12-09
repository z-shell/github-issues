# `GITHUB-ISSUES`

## Homepage link: [z-shell/zsh-github-issues](https://github.com/z-shell/zsh-github-issues)

| **Package source:** | Tarball |       Git        | Node | Gem |
|:-------------------:|:-------:|:----------------:|:----:|:---:|
|     **Status:**     |    -    | + <br> (default) |  –   |  –  |

[ZI](https://github.com/z-shell/zi) can use the NPM package registry
to automatically:

- get the plugin's Git repository OR release-package URL,
- get the list of the recommended ices for the plugin,
  - there can be multiple lists of ices,
  - the ice lists are stored in *profiles*; there's at least one profile, *default*,
  - the ices can be selectively overriden.
  - the ices can be selectively overriden.

Example ZI invocations that'll install
[z-shell/zsh-github-issues](https://github.com/z-shell/zsh-github-issues):

```zsh
# Download the default profile. Need the `@' prefix because of the `git' ice.
zi pack for @github-issues

# Download the `compact-message' profile
zi pack"compact-message" for @github-issues
```

## Default Profile

The Zinit command executed will be equivalent to:

```zsh
zi lucid id-as"GitHub-notify" \
 on-update-of'~/.cache/zsh-github-issues/new_titles.log' \
 notify'New issue: $NOTIFY_MESSAGE' for \
    z-shell/zsh-github-issues
```

## `compact-message` Profile

Will emit the notification message without `New issue: ` prefix.

The Zinit command executed will be equivalent to:

```zsh
zi lucid id-as"GitHub-notify" \
 on-update-of'~/.cache/zsh-github-issues/new_titles.log' \
 notify'$NOTIFY_MESSAGE' for \
    z-shell/zsh-github-issues
```

<!-- vim:set ft=markdown tw=80 fo+=an1 autoindent: -->
