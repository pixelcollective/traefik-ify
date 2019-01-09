# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## Unreleased

- CircleCI configuration

## [0.0.2] - 2019-01-08

### Fixed

- Nginx directives route permalinks properly.

### Added

- Add Changelog
- Added traefik/config/docker nginx directives
- [wafflebot](https://waffle.io/pixelcollective/traefik-ify)
- Codacy code quality auditing
- Hound code quality auditing

### Changed

- Improve and update documentation.
- Change Docker network name from `traefikpress` to `traefikify`.
- All Docker environment_variables are configurable via Bedrock's env.

### Removed

- markdownlint.js support
- Bedrock files in example.com which are not needed to run it as a simple example.
