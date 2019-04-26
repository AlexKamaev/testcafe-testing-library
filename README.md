<div align="center">
<h1>testcafe-testing-library</h1>

<a href="https://www.emojione.com/emoji/1f405">
<img height="80" width="80" alt="goat" src="https://raw.githubusercontent.com/benmonro/testcafe-testing-library/master/other/goat.png" />
</a>

<p>Testcafe selectors and utilities that encourage good testing practices laid down by `dom-testing-library`.</p>

[**Read the docs**](https://testing-library.com/cypress) | [Edit the docs](https://github.com/alexkrolick/testing-library-docs)

</div>

<hr />

[![Build Status][build-badge]][build]
[![Code Coverage][coverage-badge]][coverage]
[![version][version-badge]][package]
[![downloads][downloads-badge]][npmtrends]
[![MIT License][license-badge]][license]

[![All Contributors](https://img.shields.io/badge/all_contributors-10-orange.svg?style=flat-square)](#contributors)
[![PRs Welcome][prs-badge]][prs]
[![Code of Conduct][coc-badge]][coc]

[![Watch on GitHub][github-watch-badge]][github-watch]
[![Star on GitHub][github-star-badge]][github-star]
[![Tweet][twitter-badge]][twitter]

<div align="center">
<a href="https://testingjavascript.com">
<img width="500" alt="TestingJavaScript.com Learn the smart, efficient way to test any JavaScript application." src="https://raw.githubusercontent.com/kentcdodds/cypress-testing-library/master/other/testingjavascript.jpg" />
</a>
</div>

## The problem

You want to use [dom-testing-library](https://github.com/kentcdodds/dom-testing-library) methods in your [Testcafe](https://devexpress.github.io/testcafe/) tests.

## This solution

This allows you to use all the useful [dom-testing-library](https://github.com/kentcdodds/dom-testing-library) methods in your tests.

## Table of Contents

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Installation](#installation)
  - [With typescript](#with-typescript)
- [Usage](#usage)
- [Other Solutions](#other-solutions)
- [Contributors](#contributors)
- [LICENSE](#license)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Installation

This module is distributed via [npm][npm] which is bundled with [node][node] and
should be installed as one of your project's `devDependencies`:

```
npm install --save-dev testcafe-testing-library
```

### With typescript

TODO: Add typescript support

<!--
Typings are defined under `cypress-testing-library/typings`, and should be added as follows in `tsconfig.json`:

```json
{
  "compilerOptions": {
    "types": ["cypress", "../cypress-testing-library/typings"]
  }
}
```
-->

## Usage

`testcafe-testing-library` provides custom Selectors allowing you to query the
dom.

Add `testcafe-testing-library` to your test fixture's `beforeEach` hook:

```javascript
import {
  getByText, //or any other queries you want
  addTestcafeTestingLibrary,
} from 'testcafe-testing-library'

fixture`selectors`.beforeEach(addTestcafeTestingLibrary)
  .page`http://localhost:13370`
```

You can now import & use `getBy`, `getAllBy`, `queryBy` and `queryAllBy`
selectors in your tests.
[See `dom-testing-library` API for reference](dom-testing-library/api-queries.md)

## Examples

To show some simple examples (from
[https://github.com/benmonro/testcafe-testing-library/blob/master/tests/testcafe/selectors.js](https://github.com/benmonro/testcafe-testing-library/blob/master/tests/testcafe/selectors.js)):

```javascript
test('getByPlaceHolderText', async t => {
  await t.typeText(
    getByPlaceholderText('Placeholder Text'),
    'Hello Placeholder',
  )
})
test('getByText', async t => {
  await t.click(getByText('getByText'))
})

test('getByLabelText', async t => {
  await t.typeText(
    getByLabelText('Label For Input Labelled By Id'),
    'Hello Input Labelled By Id',
  )
})
```

## Other Solutions

I'm not aware of any, if you are please [make a pull request][prs] and add it
here!

## LICENSE

MIT

[npm]: https://www.npmjs.com/
[node]: https://nodejs.org
[build-badge]: https://img.shields.io/travis/kentcdodds/cypress-testing-library.svg?style=flat-square
[build]: https://travis-ci.org/kentcdodds/cypress-testing-library
[coverage-badge]: https://img.shields.io/codecov/c/github/kentcdodds/cypress-testing-library.svg?style=flat-square
[coverage]: https://codecov.io/github/kentcdodds/cypress-testing-library
[version-badge]: https://img.shields.io/npm/v/cypress-testing-library.svg?style=flat-square
[package]: https://www.npmjs.com/package/cypress-testing-library
[downloads-badge]: https://img.shields.io/npm/dm/cypress-testing-library.svg?style=flat-square
[npmtrends]: http://www.npmtrends.com/cypress-testing-library
[license-badge]: https://img.shields.io/npm/l/cypress-testing-library.svg?style=flat-square
[license]: https://github.com/kentcdodds/cypress-testing-library/blob/master/LICENSE
[prs-badge]: https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square
[prs]: http://makeapullrequest.com
[donate-badge]: https://img.shields.io/badge/$-support-green.svg?style=flat-square
[coc-badge]: https://img.shields.io/badge/code%20of-conduct-ff69b4.svg?style=flat-square
[coc]: https://github.com/kentcdodds/cypress-testing-library/blob/master/other/CODE_OF_CONDUCT.md
[github-watch-badge]: https://img.shields.io/github/watchers/kentcdodds/cypress-testing-library.svg?style=social
[github-watch]: https://github.com/kentcdodds/cypress-testing-library/watchers
[github-star-badge]: https://img.shields.io/github/stars/kentcdodds/cypress-testing-library.svg?style=social
[github-star]: https://github.com/kentcdodds/cypress-testing-library/stargazers
[twitter]: https://twitter.com/intent/tweet?text=Check%20out%20cypress-testing-library%20by%20%40kentcdodds%20https%3A%2F%2Fgithub.com%2Fkentcdodds%2Fcypress-testing-library%20%F0%9F%91%8D
[twitter-badge]: https://img.shields.io/twitter/url/https/github.com/kentcdodds/cypress-testing-library.svg?style=social
[emojis]: https://github.com/kentcdodds/all-contributors#emoji-key
[all-contributors]: https://github.com/kentcdodds/all-contributors
[dom-testing-library]: https://github.com/kentcdodds/dom-testing-library
[cypress]: https://www.cypress.io/
