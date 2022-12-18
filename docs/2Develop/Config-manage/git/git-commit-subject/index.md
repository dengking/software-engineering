# git commit subject



stackoverflow [How to do a git commit with a subject line and message body?](https://stackoverflow.com/questions/40505643/how-to-do-a-git-commit-with-a-subject-line-and-message-body) # [A](https://stackoverflow.com/a/40506149) :

If you prefer to do everything from a single command (or you write a script that needs to call `git commit` and this interactive way of committing is not an option) then you can provide the commit subject and the commit message body by [using the `-m` argument two times](https://git-scm.com/docs/git-commit):

```shell
$ git commit -m "this is the subject" -m "this is the body"
```



## karma-runner [Git Commit Msg](http://karma-runner.github.io/6.3/dev/git-commit-msg.html)

### Allowed `<type>` values: [#](http://karma-runner.github.io/6.3/dev/git-commit-msg.html#allowed-type-values)

- **feat** for a new feature for the user, not a new feature for build script. Such commit will trigger a release bumping a MINOR version.
- **fix** for a bug fix for the user, not a fix to a build script. Such commit will trigger a release bumping a PATCH version.
- **perf** for performance improvements. Such commit will trigger a release bumping a PATCH version.
- **docs** for changes to the documentation.
- **style** for formatting changes, missing semicolons, etc.
- **refactor** for refactoring production code, e.g. renaming a variable.
- **test** for adding missing tests, refactoring tests; no production code change.
- **build** for updating build configuration, development tools or other changes irrelevant to the user.



## [fteem](https://github.com/fteem)/**[git-semantic-commits](https://github.com/fteem/git-semantic-commits)**



New command -> what it does:

- `git feat "commit message here"` -> `git commit -m 'feat: commit message here'`
- `git docs "commit message here"` -> `git commit -m 'docs: commit message here'`
- `git chore "commit message here"` -> `git commit -m 'chore: commit message here'`
- `git fix "commit message here"` -> `git commit -m 'fix: commit message here'`
- `git refactor "commit message here"` -> `git commit -m 'refactor: commit message here'`
- `git style "commit message here"` -> `git commit -m 'style: commit message here'`
- `git test "commit message here"` -> `git commit -m 'test: commit message here'`
- `git localize "commit message here"` -> `git commit -m 'localize: commit message here'`



## sparkbox [Semantic Commit Messages](https://sparkbox.com/foundry/semantic_commit_messages)



```
chore: add Oyster build script
docs: explain hat wobble
feat: add beta sequence
fix: remove broken confirmation message
refactor: share logic between 4d3d3d3 and flarhgunnstow
style: convert tabs to spaces
test: ensure Tayne retains clothing
```



## chore

### stackoverflow [When to use "chore" as type of commit message?](https://stackoverflow.com/questions/26944762/when-to-use-chore-as-type-of-commit-message) # [A](https://stackoverflow.com/a/26944812)

You can see a short definition in "[Git Commit Msg](http://karma-runner.github.io/6.3/dev/git-commit-msg.html)":

> **`chore`**: updating grunt tasks etc; no production code change