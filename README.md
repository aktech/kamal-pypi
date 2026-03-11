# kamal-pypi

[Kamal](https://github.com/basecamp/kamal) packaged for PyPI — install it with `pip` instead of managing a Ruby toolchain.

## Why?

Kamal is a great deployment tool, but it's written in Ruby. If your team works in Python (or any non-Ruby stack), installing Kamal means setting up Ruby, RubyGems, and Bundler just to get a single CLI tool. This project eliminates that friction by packaging Kamal as a standalone binary inside a Python wheel.

Under the hood, [Tebako](https://github.com/tamatebako/tebako) compiles Kamal and its Ruby runtime into a single self-contained executable, and [ruby-to-wheel](https://github.com/aktech/ruby-to-wheel) wraps it into a Python wheel with the proper entry points.

## Install

```bash
pip install kamal
```

or with [uv](https://github.com/astral-sh/uv):

```bash
uv pip install kamal
```

## Usage

```bash
kamal version
kamal deploy
kamal setup
```

All Kamal commands work exactly as documented at [kamal-deploy.org](https://kamal-deploy.org).

## Platforms

| Platform | Wheel tag |
|---|---|
| Linux x86_64 | `manylinux_2_17_x86_64` |
| Linux ARM64 | `manylinux_2_17_aarch64` |
| macOS ARM64 (Apple Silicon) | `macosx_11_0_arm64` |

## Requirements

- Python >= 3.10
- On minimal Linux containers (e.g. `python:slim`), you may need to install `libyaml-0-2`:
  ```bash
  apt-get install libyaml-0-2
  ```
