Git subtree was an interesting solution for managing multiple projects within a single repository in a way that each sub-project could evolve independently while still being part of a larger codebase. However, with the rise of monorepos and the advancements in tooling for them, Git subtree has lost some of its popularity, especially in environments with microservices and Dockerization.

Works together with the next archived repos:
- [shared-ethereal-boilerplate-subtree](https://github.com/mainset/shared-ethereal-boilerplate-subtree)
- [redux-shared-store](https://github.com/mainset/redux-shared-store)

```bash
git remote add shared-ethereal-boilerplate-src git@github.com:mainset/shared-ethereal-boilerplate-subtree.git
```

Add subtree to the specific folder (by using --prefix)
```bash
git subtree add --prefix src/shared shared-ethereal-boilerplate-src master --squash
```

Updating remote repo
```bash
git fetch redux-shared-store-subtree master
```

Updating local changes
```bash
git subtree pull --prefix src/redux-shared-store redux-shared-store-subtree master --squash
```

Contributing back upstream
```bash
git subtree push --prefix=.vim/bundle/tpope-vim-surround/ durdn-vim-surround master
```
