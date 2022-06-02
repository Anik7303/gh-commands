# Git Commands

## Cloning and Existing Repository:

```bash
git clone <repository_url> <directory_name>
```

## Configuring git:

```bash
git config --global user.name <name>
git config --global user.email <email_address>
git config --global core.editor <editor_name> # prefered editor name eg. vim, nano

# show global configs
git config --global --list
# show local configs
git config --list
```

## Checking the Status of Repository:

```bash
git status
git status -s # short status
```

## Tracking New Files:

```bash
git add <file_name>

git add -A # add all files
git add . # add all files
```

## Ignoring Files:

```bash
# in .gitignore file
# ignore all files with extension .c or .a
*.[ca]
# ignore all files with extension .js or .jsx
*.jsx?
# ignore all files ending with number 0 to 9
*[0-9]
# only ignore the TODO file in the current directory, not subdir/TODO
/TODO
# ignore all files in any directory named build
/build
# ignore doc/notes.txt, but not doc/server/arch.txt
doc/*.txt
# ignore all .pdf files in the doc/ directory and any of its subdirecotries
doc/**/*.pdf
# more gitignore file examples in https://github.com/github/gitignore
```

## Viewing Staged and Unstaged Changes:

```bash
git diff # view unstaged changes

git diff --staged # view staged changes
git diff --cached # view staged changes
```

## Committing Changes:

```bash
git commit

git commit -m <message>

git commit -a # to also add modified files to commit
```

## Removing Files:

```bash
git rm <file_name> # remove from both tracked list and directory
git rm --cached <file_name> # removes only from tracked list
```

## Moviing Files:

```bash
git mv <file_from> <file_to>
```

## Viewing Commit History:

```bash
git log

git log -<n> # replace n with any number, shows last n commits

git log -p # shows the difference introduced in each commit
git log --patch # shows the difference introduced in each commit

git log --stat # show abbreviated stats for each commit

# --pretty changes the log output to formats other than the default
# --pretty=oneline prints each commit on a single line
# --pretty=short, --pretty=full, --pretty=fuller shows the output in roughly the same format
# but with less or more information, respectively
git log --pretty=oneline

# --pretty=format lists some of the more usefull specifiers that format takes.
git log --pretty=format:"%h - %an, %ar : %s"

git log --graph # adds a nice little ASCII graph showing branch and merge history
git log --pretty=format:"%h %s" --graph
```

### Useful Specifiers for `git log --pretty=format`

| Specifier | Description of Output                         |
| --------- | --------------------------------------------- |
| %H        | Commit hash                                   |
| %h        | Abbreviated commit hash                       |
| %T        | Tree hash                                     |
| %t        | Abbreviated tree hash                         |
| %P        | Parent hashes                                 |
| %p        | Abbreviated parent hashes                     |
| %an       | Author name                                   |
| %ae       | Author email                                  |
| %ad       | Author date(format respects the --date=option |
| %ar       | Author date, relative                         |
| %cn       | Committer name                                |
| %ce       | Committer email                               |
| %cd       | Committer date                                |
| %cr       | Committer date, relative                      |
| %s        | Subject                                       |

### Common options to `git log`:

| Option          | Description                                                                                                  |
| --------------- | ------------------------------------------------------------------------------------------------------------ |
| -p or --patch   | Show the patch introduced with each commit                                                                   |
| --stat          | Sho statistics for files modified in each commit                                                             |
| --shortstat     | Display only the changed/insertions/deletions line from the `--stat` command                                 |
| --name-only     | Show the list of files modified after the commit infromation                                                 |
| --name-status   | Show the list of files affected with added/modified/deleted information as well                              |
| --abbrev-commit | Show only the first few characters of the SHA-1 checksum instead of all 40                                   |
| --relative-date | Display the date in a relative format instead of using the full date format                                  |
| --graph         | Display an ASCII graph of the branch and merge history beside the log output                                 |
| --pretty        | Show commits in an alternate format. Option values include `oneline`, `short`, `full`, `fuller` and `format` |
| --oneline       | Shorthand for `--pretty=oneline --abbrev-commit` used together                                               |
