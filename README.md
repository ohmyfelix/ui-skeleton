# UI skeleton

A Nette application skeleton with Vite, Tailwind CSS, and Alpine.js.

## Requirements

- PHP 8.4 or newer
- [Composer](https://getcomposer.org/)
- Node.js and npm

## Create a project

```bash
composer create-project contributte/ui-skeleton acme
cd acme
make init
make project
npm ci
```

`make init` creates `config/local.neon`; `make project` installs Composer dependencies and prepares the writable runtime directories.

## Local development

Start the PHP application:

```bash
make dev
```

Open [http://localhost:8000](http://localhost:8000). Build frontend assets in a second terminal:

```bash
npm run watch
```

Use `npm run build` for a production asset build. `make build` installs npm dependencies and builds production assets, while `make assets` starts the asset watcher.

## Vite assets

Vite builds `assets/js/app.ts` into `www/dist/` and writes a manifest there. Development builds use stable filenames; production builds use hashed filenames. The application reads this manifest through the UI integration, so deploy the generated `www/dist/` files with the application.

## Configuration

Shared application configuration is in `config/config.neon`. Keep local parameters and service overrides in the ignored `config/local.neon`, created from `config/local.neon.example`.

## Quality assurance

```bash
make qa
make tests
```

`make qa` runs coding-standard and PHPStan checks. `make tests` runs Nette Tester tests from `tests/`.
