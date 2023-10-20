<p align="center">
  <br />
  <a title="Learn more about Vitest for VSCode" href="https://github.com/vitest-dev/vscode"><img src="./img/cover.png" alt="Vitest for VSCode Logo" width="50%" /></a>

</p>

<h2 align="center">
  <b>Vitest for VSCode</b>
</h2>

<br />

![](https://i.ibb.co/bJCbCf2/202203292020.gif)

> This extension is powered by
> [vscode testing api](https://code.visualstudio.com/api/extension-guides/testing).

# Features

- Run/debug vitest tests in vscode
- Watch mode is supported 🎊. Test reruns are blazing fast

![Watch Mode](https://i.ibb.co/YRhJj9f/Screen-Recording-2022-05-21-at-20-09-20.gif)

# Requirements

- Require VSCode's version >= July 2021 (version 1.59).
- Require Vitest's version >= v0.12.0

# Config

- `vitest.enable`: This plugin will try to detect whether the current project is
  set up with Vitest to activate itself. When it failed, you can enable the
  plugin manually
- `vitest.nodeEnv`: The env passed to runner process in addition to
  `process.env`
- `vitest.commandLine`: The command line to start vitest tests. **It should have with the ability
  to append extra arguments**. For example
  `npx vitest` or `yarn test --`.(This is a workspace setting. Do not change it in
  the user setting directly, which will affect all the projects you open)
- `vitest.include`: Include glob for test files. Default:
  `[\"**/*.{test,spec}.{js,mjs,cjs,ts,mts,cts,jsx,tsx}\"]`
- `vitest.exclude`: Exclude globs for test files. Default:
  `[\"**/node_modules/**\", \"**/dist/**\", \"**/cypress/**\", \"**/.{idea,git,cache,output,temp}/**\"]`
- `vitest.debugExclude`: Automatically skip files covered by these glob patterns. Default:
  `[\"<node_internals>/**\", \"**/node_modules/**\"]`
- `vitest.rootPath`: The path to the root of a project containing a Vitest configuration.
  This can be used if your project does not exist at the root of your workspace.

# Screenshots

**Filter tests by status**

<img src="https://i.ibb.co/K903GYL/Screen-Recording-2022-03-29-at-20-41-54.gif"/>

**Debug**

<img src="https://i.ibb.co/SXtF6Yp/Screen-Recording-2022-03-29-at-20-49-54.gif"/>

**Inspect console output**

![](https://i.ibb.co/gMZWXZQ/Screen-Recording-2022-03-29-at-20-59-31.gif)

# FAQ

#### **How can I use it in monorepo?**

It's not well supported yet. But you can use VS Code workspace as a workaround for now. Each folder of the workspace can have its own vitest extension config.

#### **How can I use this extension when tests are under a sub directory?**

You can use VS Code command `add folder to workspace` to add the sub directory. The extension should work fine.

#### **`test.each` is not working**

Dynamic test name is not supported yet. This extension currently relies on the babel parser to calculate the positions of tests statically.

Related issue: https://github.com/vitest-dev/vscode/issues/133
