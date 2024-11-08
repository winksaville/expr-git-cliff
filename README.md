# Experiment with git-cliff

The [git-cliff] is an git extension that allows for creating
CHANGELOG.md files.

## Test generating a CHANGELOG.md

To get quick look on the how the first N lines, 10 in this case,
of unreleased commits would look in CHANGLOG.md but just showing
them on the terminal run:

```bash
$ git cliff | head -10
# Changelog

All notable changes to this project will be documented in this file.

## [unreleased]

- wip: Update README.md

## [0.3.1] - 2024-11-08

```

If you'd like see what it would be with a `tag` such as `v0.3.2` run:

```bash
$ git cliff --tag v0.3.2 | head -10
# Changelog

All notable changes to this project will be documented in this file.

## [0.3.2] - 2024-11-08

- wip: Update README.md

## [0.3.1] - 2024-11-08

```

To render to a test file like `test.md` run:

```bash
$ git cliff --tag v0.3.2 -o test.md
$ head -10 test.md
# Changelog

All notable changes to this project will be documented in this file.

## [0.3.2] - 2024-11-08

- wip: Update README.md

## [0.3.1] - 2024-11-08

```

## Build final CHANGELOG.md

- Change Cargo.toml version to the desired value like `v0.3.2`
- Update Cargo.toml with the new version
- Update README.md and any other files
- Create a `wip: Bump version to v0.3.2` commit
- Run build
- Run the following command to generate the CHANGELOG.md

```bash
git cliff --tag v0.3.2 -o CHANGELOG.md
```

- Verify the `CHANGELOG.md` file and commit the changes
- Tag the commit with the version number

git tag v0.3.2


## License

Licensed under either of

- Apache License, Version 2.0 ([LICENSE-APACHE](LICENSE-APACHE) or http://apache.org/licenses/LICENSE-2.0)
- MIT license ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in the work by you, as defined in the Apache-2.0 license, shall
be dual licensed as above, without any additional terms or conditions.
