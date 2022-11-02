# Setup
## Plug and play.
1. Create scripts directory (if you have one skip this step)
```sh
mkdir -p ~/scripts/migrate_down
```
2. Pull the files
```sh
cd ~/scripts/migrate_down
git init
git remote add origin git@github.com:patryksink/migration_script.git
git fetch
git pull origin main
```
2. Depending on the shell type used add path to scripts folder
2.1 bash -> ~/.bashrc
2.2 zsh -> ~/.zshrc
```sh
PATH=$PATH:$HOME/scripts/migrate_down
```
## Custom Setup
If script versioning is not needed and want to keep your script folder neet.
1. Create scripts directory (if you have one skip this step)
```sh
mkdir ~/scripts
```
2. Moving file to `~/scripts` directory
- Pull the file
- You can rename the file and place it directly in the `~/scripts` directory
- You can instead follow the process of 1 setup (only in diferent directory) and simply put simplink to the `~/scripts` directory
3. Depending on the shell type used add `PATH` to scripts folder
3.1 bash -> ~/.bashrc
3.2 zsh -> ~/.zshrc
```sh
PATH=$PATH:$HOME/scripts
```
# Usage
```sh
migrate_down git_branch
```
## Options
`-c` - switch to target branch after migrations downgrade
# Additional behaviour
- Not providing branch will diplay all branch list
- Incorect branch name will diplay all branch list
