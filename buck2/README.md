# Buck2 Project

This directory contains a [Buck2](https://buck2.build) project used to demonstrate parallel queues.

## Structure

- **Word packages**: `alpha/`, `bravo/`, `charlie/`, `delta/`, `echo/`, `foxtrot/`, `golf/`,
  `hotel/`, `indigo/`, `juliet/`, `kilo/`
  - Each package contains a `.txt` file with words and a `BUCK` file declaring a `filegroup`
- **Toolchains**: `toolchains/` registers the prelude's demo toolchains
- The prelude is the copy bundled with the `buck2` binary (`[external_cells] prelude = bundled`)

## Setup

Install `buck2` from the [releases page](https://github.com/facebook/buck2/releases), then:

```bash
cd buck2
buck2 targets //...
buck2 build //...
```

## Impacted Targets

Set `build = "buck2"` and `change_code_path = "buck2"` in `.config/mq.toml` to have the PR Factory
edit files here and upload impacted targets computed from the Buck2 graph:

```bash
python3 tools/detect_impacted_buck2_targets.py --base=main
```
