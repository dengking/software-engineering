# git配置文件



`.gitconfig`

```ini
[user]
	name = dengkai01
	#email = 2238897886@qq.com
	email = 2238897886@qq.com
[credential "helperselector"]
	selected = <no helper>
[filter "lfs"]
	smudge = git-lfs smudge -- %f
	process = git-lfs filter-process
	required = true
	clean = git-lfs clean -- %f
[difftool "sourcetree"]
	cmd = '' \"$LOCAL\" \"$REMOTE\"
[mergetool "sourcetree"]
	cmd = "'' "
	trustExitCode = true
[gui]
	recentrepo = D:/NetEase/auto-c-wrapper
[core]
	excludesfile = C:\\Users\\dengkai01\\Documents\\gitignore_global.txt
	autocrlf = true
	safecrlf = false

```

