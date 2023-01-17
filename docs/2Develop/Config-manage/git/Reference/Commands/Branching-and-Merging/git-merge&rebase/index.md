# git merge and rebase

## 简单粗暴的merge方式

首先尝试的是`git rebase`，但是rebase失败了，后来请教了同事，他的思路是：

reset

stash

merge

apply （replay）

```shell
 88  git rebase --abort # undo rebase
 89  git status
 90  git pull
 91  git status
 92  git branch
 93  git checkout 95950f78fe487304019751140cba5336a7aecb7c
 94  git status
 95  git checkout feature/4.5.0/litesdk/4.5.901-ASAN
 96  git log
 97  git reset 95950f78fe487304019751140cba5336a7aecb7c # previous commit of the commit you want to undo
 98  git status
 99  git stash
100  git stats
101  git status
102  git stash apply stash@{0}
103  git add -u
104  git status
105  git add mobile-sdk/android/nrtc/asan
106  git status
107  git stash
108  git status
109  git log
110  git push origin feature/4.5.0/litesdk/4.5.901-ASAN -f
111  git push origin feature/4.5.0/litesdk/4.5.901-ASAN -f
112  git status
113  git submodule update --init --recursive -j 5
114  conan install . -s os=Android
115  git stash apply stash@{0}
116  git status
117  git diff build/android/build_android.py
118  git status
119  git add nertcsdk/src/lite/wrapper/android/build.gradle
120  git status
121  git diff build/android/build_android.py
122  git add build/android/build_android.py
123  git add build/android/build_android.py -f
124  git status
125  git diff --cached build/android/build_android.py
126  ls
127  git status
128  git reset build/android/build_android.py
129  git status
130  git status
131  history

```