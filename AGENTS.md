# Repository Guidelines

## Project Structure & Module Organization

This is a small Rust binary crate. `Cargo.toml` defines the package and Rust 2024 edition; `Cargo.lock` records the resolved dependencies. The application entry point is `src/main.rs`. There are no separate modules, tests, or assets yet. Put new application modules under `src/` and declare them from `main.rs`; add integration tests under `tests/` when behavior needs testing through the public binary interface. Cargo writes build output to `target/`, which is ignored by Git.

## Build, Test, and Development Commands

- `cargo run` builds and runs the binary locally.
- `cargo build` checks that the project compiles and produces a debug binary.
- `cargo test` runs unit, integration, and documentation tests as they are added.
- `cargo fmt --check` checks Rust formatting without changing files; use `cargo fmt` to apply it.
- `cargo clippy --all-targets -- -D warnings` checks for common Rust mistakes and treats warnings as errors.

Run the formatting, Clippy, and test commands before opening a pull request.

## Coding Style & Naming Conventions

Follow standard Rust style and let `rustfmt` manage indentation and line wrapping (four spaces, no tabs). Use `snake_case` for functions, modules, and variables; `PascalCase` for types and traits; and `SCREAMING_SNAKE_CASE` for constants. Keep `main.rs` focused on startup and move substantial logic into clearly named modules. Prefer standard-library features unless a dependency solves a concrete need.

## Testing Guidelines

Rust's built-in test harness is the current testing framework; no coverage target is configured. Place focused unit tests beside the code in `#[cfg(test)]` modules, and use `tests/*.rs` for integration tests. Name tests for the behavior they verify, such as `prints_expected_message`. Run `cargo test` after behavior changes.

## Commit & Pull Request Guidelines

The repository has no commits yet, so it has no established commit-message convention. Use short, imperative subjects that describe the change, such as `Add command-line greeting`. Keep pull requests focused; describe the behavior changed, note how it was tested, and link an issue when one exists. Include screenshots only for changes with visible UI output.
