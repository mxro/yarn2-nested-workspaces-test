# yarn2-nested-workspaces-test

This project demonstrates the usage of nested worktrees using [Yarn 2 Berry](https://yarnpkg.com/). Find out more about Yarn workspaces here: [Yarn 2 Features Workspaces](https://yarnpkg.com/features/workspaces).

To run this project, first install latest yarn (v.1.22+). Then run `yarn`.

Finally, go into `workspaces/workspace2/packages/package2` and run:

`yarn node index.js`

This is the index.js file:

```
const package1 = require('package1');

package1.hi();
```

It references package1 in a different worktree:

```
{
  "name": "package2",
  "dependencies": {
    "package1": "workspace:workspaces/workspace1/packages/package1"
  }
}
```