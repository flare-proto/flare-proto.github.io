# Utility Commands
## Git

### Wrong Email
```bash
git filter-branch --env-filter '
OLD_EMAIL="wrong.email@example.com"
CORRECT_NAME="Flare"
CORRECT_EMAIL="correct.email@example.com"

if [ "$GIT_COMMITTER_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_COMMITTER_NAME="$CORRECT_NAME"
    export GIT_COMMITTER_EMAIL="$CORRECT_EMAIL"
fi
if [ "$GIT_AUTHOR_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_AUTHOR_NAME="$CORRECT_NAME"
    export GIT_AUTHOR_EMAIL="$CORRECT_EMAIL"
fi
' --tag-name-filter cat -- --branches --tags
```
```bash
git push --force --all
git push --force --tags
```