# Dotfiles

Dotfiles managed by chezmoi for linux and mac

## SSH Keys

SSH keys must be stored in 1password and corresponding public keys added to repo

1. Install 1password desktop app and 1password-cli
2. Enable SSH Agent in settings on the 1password app and make sure cli integration is working
3. Create key in 1password
    - `op item create --category ssh --title "My SSH Key"`
4. Add 1password ssh agent and test to make sure you can see the key
    - `export SSH_AUTH_SOCK=~/Library/Group\ Containers/2BUA8C4S2C.com.1password/t/agent.sock`
    - `ssh-add -l`
5. Create a public key file in ~/.ssh for work and personal keys
    - `chezmoi add ~/.ssh/github_personal.pub`
    - `chezmoi add ~/.ssh/github_work.pub`
6. Commit and push new keys `chezmoi cd`

 
Install chezmoi with brew first or just run

```
sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply kevinbagel
```
## Load iTerm2 settings

```
defaults write com.googlecode.iterm2.plist PrefsCustomFolder -string "~/.config/iterm2"
defaults write com.googlecode.iterm2.plist LoadPrefsFromCustomFolder -bool true
```
Then restart iTerm
