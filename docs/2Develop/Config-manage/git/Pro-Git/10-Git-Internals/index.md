# 10. [Git Internals](https://git-scm.com/book/en/v2/Git-Internals-Plumbing-and-Porcelain)

## 10.1 [Plumbing and Porcelain](https://git-scm.com/book/en/v2/Git-Internals-Plumbing-and-Porcelain)

This book covers primarily how to use Git with 30 or so subcommands such as `checkout`, `branch`, `remote`, and so on. But because Git was initially a toolkit for a version control system rather than a full user-friendly VCS, it has a number of subcommands that do low-level work and were designed to be chained together UNIX-style or called from scripts. These commands are generally referred to as Git’s “plumbing” commands, while the more user-friendly commands are called “porcelain” commands.