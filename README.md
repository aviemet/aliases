# Avram's Dotfiles

To start, create a bare repository in your home folder:

```bash
git init --bare $HOME/.cfg
```

Set a local alias for `config` to easily interact with our dotfiles:

```bash
alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'
config config --local status.showUntrackedFiles no
```

Using this command, or manually, add the alias to your terminal config:

```bash
echo "alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'" >> $HOME/.zshrc
```

Make sure the `.cfg` folder is in `.gitignore`

Clone the files to your home folder and run checkout:

```bash
git clone --bare https://github.com/aviemet/aliases.git $HOME/.cfg
alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'
config checkout
```

If you are prompted regarding collisions, backup the offending files and run `config checkout` again.

[Credit to this article](https://www.atlassian.com/git/tutorials/dotfiles)
