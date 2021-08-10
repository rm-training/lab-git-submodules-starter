
- [Sample Project](https://github.com/rm-training/dummy-main-project)
- [Basic Starter](https://github.com/rm-training/lab-git-submodules-starter)

# Demo / Lab setup

```bash
git clone https://github.com/rm-training/lab-git-submodules-starter
cd lab-git-submodules-starter
rm -Rf .git
```

You'll be left with:

```bash
tree
.
├── main-project
│   ├── first
│   └── lib
│       └── module-a
│           ├── file3
│           ├── first
│           └── second
└── simulated-remotes
    ├── module-a
    │   ├── first
    │   └── second
    └── module-b
        └── first
```

# Module Project(s)

For both `module-a` and `module-b`:

```bash
cd module-a
git init
git add .
git commit -m 'A: First Commit'
git config --local receive.denyCurrentBranch warn

cd module-b
git init
git add .
git commit -m 'B: First Commit'
git config --local receive.denyCurrentBranch warn
```

# Main Project

```bash
cd main-project
git init
git add .
git commit -m 'Main: First Commit'
```

Set the configs:
```bash
git config --local submodule.recurse true
git config --local diff.submodule log    
git config --local status.submoduleSummary true
```

Then add your submodule(s):
```bash
git submodule add ../simulated-remotes/module-a lib/module-a
```
