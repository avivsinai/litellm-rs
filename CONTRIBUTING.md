# Contributing to litellm-rs

Thank you for your interest in contributing to litellm-rs!

## Development Setup

### Prerequisites

- Rust 1.88+ (check with `rustc --version`)
- Git

### Getting Started

```bash
# Clone the repository
git clone https://github.com/avivsinai/litellm-rs.git
cd litellm-rs

# Build
cargo build

# Run tests (no API keys needed - uses WireMock)
cargo test

# Lint
cargo clippy

# Format
cargo fmt
```

## Code Style

- Follow Rust conventions and idioms
- Run `cargo fmt` before committing
- Ensure `cargo clippy` passes without warnings
- Write tests for new functionality
- Use `thiserror` for error types
- Async with `tokio`

## Pull Request Process

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Run tests and linting (`cargo test && cargo clippy`)
5. Commit with a descriptive message
6. Push to your fork
7. Open a Pull Request

## Commit Messages

Use clear, descriptive commit messages:

- `feat: add Mistral provider support`
- `fix: handle empty choices in completion response`
- `docs: add streaming usage example`
- `refactor: extract retry logic into shared module`
- `test: add integration tests for Gemini video generation`

## Adding a New Provider

1. Create `src/providers/your_provider.rs`
2. Implement the provider trait following the pattern in `openai_compat.rs` or `anthropic.rs`
3. Register it in `src/providers/mod.rs`
4. Add integration tests in `tests/integration_providers.rs` using WireMock
5. Update `data/provider_endpoints_support.json` if applicable

## Reporting Issues

When reporting issues, please include:

- Rust version (`rustc --version`)
- Operating system
- Steps to reproduce
- Expected vs actual behavior
- Relevant error messages

## License

By contributing, you agree that your contributions will be licensed under the MIT License.
