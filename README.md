# clang-format-metal Pre-commit Hook

This repository contains a pre-commit hook for formatting C++ and Metal shader files using `clang-format`. It is designed to ensure consistent code styling by automatically formatting `.cpp`, `.h`, `.hpp`, and `.metal` files upon commit.

## Requirements

- `pre-commit`: This hook relies on the [pre-commit](https://pre-commit.com/) framework. Ensure you have `pre-commit` installed in your development environment.
- `clang-format`: You must have `clang-format` installed on your system. This hook calls `clang-format` directly to format the specified file types.

## Installation

1. **Install `pre-commit`** (if not already installed):
   ```bash
   pip install pre-commit
   ```
   or, if you prefer using Homebrew on macOS:
   ```bash
   brew install pre-commit
   ```

2. **Install `clang-format`** (if not already installed):
   - On macOS:
     ```bash
     brew install clang-format
     ```
   - On Ubuntu:
     ```bash
     sudo apt-get install clang-format
     ```

3. **Add the `clang-format-metal` hook to your project** by creating or updating your `.pre-commit-config.yaml` file in the root of your repository:

   ```yaml
   repos:
     - repo: https://github.com/NripeshN/clang-format-metal
       rev: 17.0.6
       hooks:
         - id: clang-format-metal
   ```

4. **Install the pre-commit hook** into your git repository:
   ```bash
   pre-commit install
   ```

## Usage

Once installed, the `clang-format-metal` hook will automatically format `.cpp`, `.h`, `.hpp`, and `.metal` files each time you commit changes. To manually trigger formatting on all files without committing, you can run:

```bash
pre-commit run --all-files
```

## Configuration

This hook uses `clang-format` with the `-i` flag to format files in place. If you have specific `clang-format` style preferences, ensure you have a `.clang-format` configuration file in your repository's root or in an appropriate parent directory.

## Troubleshooting

- **clang-format not found**: Ensure that `clang-format` is correctly installed and available in your system's PATH. You might need to specify the path to `clang-format` in the `entry` field of the `.pre-commit-hooks.yaml` file if it's installed in a non-standard location.
- **Pre-commit hook not running**: Make sure you've run `pre-commit install` in your repository to set up the hooks.

## Contributing

Contributions to improve `clang-format-metal` are welcome! Please feel free to open issues or pull requests on our [GitHub repository](https://github.com/NripeshN/clang-format-metal).
