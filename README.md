# Setup
## Create scripts directory 
(if you have one skip this step)
```sh
mkdir ~/scripts
```
## 1 - Symlink way
1. Create repos directory (if you have one skip this step)
```sh
mkdir ~/repos
```
2. Pull the repo
```sh
cd ~/repos
git clone https://github.com/patryksink/migration_script.git
```
3. Create symlink
```sh
cd ~/scripts
ln -s ~/repos/migration_script/migrate_down
```
> In this case third argument will be command name `migrate_down` by default

4. [Add path](#add-path)

## 2 - Copy file way
If script versioning is not needed and want to keep filesystem neet, simply copy the file
1. Pull the repo
```sh
git clone https://github.com/patryksink/migration_script.git
```
3. Copy file to `~/scripts` directory
```sh
cp ./migration_script/migrate_dowm ~/scripts/{command_name}
```
> value in bracket will be command name `migrate_down` by default

4. Remove redundant folder
```sh
rm -rf ./migration_script
```
5. [Add path](#add-path)

## Add path
Depending on the shell type used add path to scripts folder
1. Copy `PATH=$PATH:$HOME/scripts` to config
- bash -> `~/.bashrc`
```sh
echo "PATH=\$PATH:\$HOME/scripts" ~/.bashrc
```
- zsh -> `~/.zshrc`
```sh
echo "PATH=\$PATH:\$HOME/scripts" ~/.zshrc
```
## Change script variables
Depending on the project doctrine command and migration location may differ so change variables acordingly
- `COMMAND` => provide your own command if project requires other Doctrine syntax
- `MIGRATION_PATH` => describes path to the migration folder from current directory
# Usage
```sh
migrate_down git_branch
```
## Options
`-c` - switch to target branch after migrations downgrade
# Additional behaviour
- Not providing branch will diplay all branch list
- Incorrect branch name will diplay all branch list
