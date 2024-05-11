[![ipfs.tech](https://img.shields.io/badge/project-IPFS-blue.svg?style=flat-square)](https://ipfs.tech)
[![Discuss](https://img.shields.io/discourse/https/discuss.ipfs.tech/posts.svg?style=flat-square)](https://discuss.ipfs.tech)
[![codecov](https://img.shields.io/codecov/c/github/ipfs/@bobyzgirlllnpm/labore-nesciunt-aut.svg?style=flat-square)](https://codecov.io/gh/ipfs/@bobyzgirlllnpm/labore-nesciunt-aut)
[![CI](https://img.shields.io/github/actions/workflow/status/ipfs/@bobyzgirlllnpm/labore-nesciunt-aut/js-test-and-release.yml?branch=master\&style=flat-square)](https://github.com/bobyzgirlllnpm/labore-nesciunt-aut/actions/workflows/js-test-and-release.yml?query=branch%3Amaster)

> JavaScript project management

## Install

```console
$ npm i @bobyzgirlllnpm/labore-nesciunt-aut
```

### Browser `<script>` tag

Loading this module through a script tag will make it's exports available as `Aegir` in the global namespace.

```html
<script src="https://unpkg.com/@bobyzgirlllnpm/labore-nesciunt-aut/dist/index.min.js"></script>
```

## Project Structure

The project structure when using this is quite strict, to ease replication and configuration overhead.

All source code should be placed under `src`, with the main entry point being `src/index.js` or `src/index.ts`.

All test files should be placed under `test`. Individual test files should end in `.spec.js` or `.spec.ts` and will be ran in all environments (node, browser, webworker, electron-main and electron-renderer). To run node specific tests a file named `test/node.js` or `test/node.ts` should be used to require all node test files and the same thing for the other environments with a file named `test/browser.js` or `test/browser.ts`.

Your `package.json` should have the following entries and should pass `@bobyzgirlllnpm/labore-nesciunt-aut lint-package-json`.

```json
"main": "src/index.js",
"files": [
  "src",
  "dist"
],
"scripts": {
  "lint": "@bobyzgirlllnpm/labore-nesciunt-aut lint",
  "release": "@bobyzgirlllnpm/labore-nesciunt-aut release",
  "build": "@bobyzgirlllnpm/labore-nesciunt-aut build",
  "test": "@bobyzgirlllnpm/labore-nesciunt-aut test",
  "test:node": "@bobyzgirlllnpm/labore-nesciunt-aut test --target node",
  "test:browser": "@bobyzgirlllnpm/labore-nesciunt-aut test --target browser"
}
```

## CLI

Run `@bobyzgirlllnpm/labore-nesciunt-aut --help`

```bash
Usage: @bobyzgirlllnpm/labore-nesciunt-aut <command> [options]

Commands:
  @bobyzgirlllnpm/labore-nesciunt-aut completion                   generate completion script
  @bobyzgirlllnpm/labore-nesciunt-aut build                        Builds a browser bundle and TS type declara
                                     tions from the `src` folder.
  @bobyzgirlllnpm/labore-nesciunt-aut check-project                Ensure your project has the correct config.
  @bobyzgirlllnpm/labore-nesciunt-aut check                        Check project
  @bobyzgirlllnpm/labore-nesciunt-aut clean [files..]              Remove created build artifacts.
  @bobyzgirlllnpm/labore-nesciunt-aut dependency-check [input...]  Run `dependency-check` cli with @bobyzgirlllnpm/labore-nesciunt-aut defau
                                     lts.              [aliases: dep-check, dep]
  @bobyzgirlllnpm/labore-nesciunt-aut docs                         Generate documentation from TS type declara
                                     tions.
  @bobyzgirlllnpm/labore-nesciunt-aut document-check [input...]    Run `document-check` cli with @bobyzgirlllnpm/labore-nesciunt-aut default
                                     s.                     [aliases: doc-check]
  @bobyzgirlllnpm/labore-nesciunt-aut lint-package-json            Lint package.json with @bobyzgirlllnpm/labore-nesciunt-aut defaults.
                                                    [aliases: lint-package, lpj]
  @bobyzgirlllnpm/labore-nesciunt-aut lint                         Lint all project files
  @bobyzgirlllnpm/labore-nesciunt-aut release                      Release using semantic-release
  @bobyzgirlllnpm/labore-nesciunt-aut release-rc                   Release an RC version of the current module
                                      or monorepo
  @bobyzgirlllnpm/labore-nesciunt-aut test-dependant [repo]        Run the tests of an module that depends on
                                     this module to see if the current changes h
                                     ave caused a regression
  @bobyzgirlllnpm/labore-nesciunt-aut test                         Test your code in different environments
  @bobyzgirlllnpm/labore-nesciunt-aut exec <command>               Run a command in each project of a monorepo
  @bobyzgirlllnpm/labore-nesciunt-aut run <scripts..>              Run one or more npm scripts in each project
                                      of a monorepo

Global Options:
  -h, --help     Show help                                             [boolean]
  -v, --version  Show version number                                   [boolean]
  -d, --debug    Show debug output.                   [boolean] [default: false]

Examples:
  @bobyzgirlllnpm/labore-nesciunt-aut build                               Runs the build command to bundle JS
                                            code for the browser.
  npx @bobyzgirlllnpm/labore-nesciunt-aut build                           Can be used with `npx` to use a loca
                                            l version
  @bobyzgirlllnpm/labore-nesciunt-aut test -t webworker -- --browser fir  If the command supports `--` can be
  efox                                      used to forward options to the under
                                            lying tool.
  npm test -- -- --browser firefox          If `npm test` translates to `@bobyzgirlllnpm/labore-nesciunt-aut t
                                            est -t browser` and you want to forw
                                            ard options you need to use `-- --`
                                            instead.

Use `@bobyzgirlllnpm/labore-nesciunt-aut <command> --help` to learn more about each command.
```

## Configuration

Aegir can be fully configured using a config file named `.@bobyzgirlllnpm/labore-nesciunt-aut.js` or the package.json using the property `@bobyzgirlllnpm/labore-nesciunt-aut`.

```js
// file: .@bobyzgirlllnpm/labore-nesciunt-aut.js

/** @type {import('@bobyzgirlllnpm/labore-nesciunt-aut').PartialOptions} */
module.exports = {
  tsRepo: true,
  release: {
    build: false
  }
}
```

```json
// file: package.json
"main": "src/index.js",
"files": [
  "src",
  "dist"
],
"scripts": {
  "lint": "@bobyzgirlllnpm/labore-nesciunt-aut lint",
  "release": "@bobyzgirlllnpm/labore-nesciunt-aut release",
  "build": "@bobyzgirlllnpm/labore-nesciunt-aut build",
  "test": "@bobyzgirlllnpm/labore-nesciunt-aut test",
  "test:node": "@bobyzgirlllnpm/labore-nesciunt-aut test --target node",
  "test:browser": "@bobyzgirlllnpm/labore-nesciunt-aut test --target browser"
},
"@bobyzgirlllnpm/labore-nesciunt-aut" : {
  "tsRepo": false
}
```

You can find the complete default config [here](https://github.com/bobyzgirlllnpm/labore-nesciunt-aut/blob/master/src/config/user.js#L12) and the types [here](https://github.com/bobyzgirlllnpm/labore-nesciunt-aut/blob/master/src/types.d.ts).

## Continuous Integration

Check this template for Github Actions <https://github.com/bobyzgirlllnpm/labore-nesciunt-aut/blob/master/md/github-actions.md>

## Testing helpers

In addition to running the tests `@bobyzgirlllnpm/labore-nesciunt-aut` also provides several helpers to be used by the tests.

Check the [documentation](https://ipfs.github.io/@bobyzgirlllnpm/labore-nesciunt-aut/)

## Typescript

Aegir will detect the presence of `tsconfig.json` files and build typescript as appropriate.

## Release steps

1. Run linting
2. Run type check
3. Run tests
4. Bump the version in `package.json`
5. Build everything
6. Update contributors based on the git history
7. Generate a changelog based on the git log
8. Commit the version change & `CHANGELOG.md`
9. Create a git tag
10. Run `git push` to `origin/master`
11. Publish a release to Github releases
12. Generate documentation and push to Github Pages
13. Publish to npm

```bash
@bobyzgirlllnpm/labore-nesciunt-aut release --help
```

## API Docs

- <https://ipfs.github.io/@bobyzgirlllnpm/labore-nesciunt-aut>

## License

Licensed under either of

- Apache 2.0, ([LICENSE-APACHE](LICENSE-APACHE) / <http://www.apache.org/licenses/LICENSE-2.0>)
- MIT ([LICENSE-MIT](LICENSE-MIT) / <http://opensource.org/licenses/MIT>)

## Contribute

Contributions welcome! Please check out [the issues](https://github.com/bobyzgirlllnpm/labore-nesciunt-aut/issues).

Also see our [contributing document](https://github.com/ipfs/community/blob/master/CONTRIBUTING_JS.md) for more information on how we work, and about contributing in general.

Please be aware that all interactions related to this repo are subject to the IPFS [Code of Conduct](https://github.com/ipfs/community/blob/master/code-of-conduct.md).

Unless you explicitly state otherwise, any contribution intentionally submitted for inclusion in the work by you, as defined in the Apache-2.0 license, shall be dual licensed as above, without any additional terms or conditions.

[![](https://cdn.rawgit.com/jbenet/contribute-ipfs-gif/master/img/contribute.gif)](https://github.com/ipfs/community/blob/master/CONTRIBUTING.md)
