# deno_python

[![Tags](https://img.shields.io/github/release/denosaurs/deno_python)](https://github.com/denosaurs/deno_python/releases)
[![deno doc](https://doc.deno.land/badge.svg)](https://doc.deno.land/https/deno.land/x/python@0.2.0/mod.ts)
[![checks](https://github.com/denosaurs/deno_python/actions/workflows/checks.yml/badge.svg)](https://github.com/denosaurs/deno_python/actions/workflows/checks.yml)
[![License](https://img.shields.io/github/license/denosaurs/deno_python)](https://github.com/denosaurs/deno_python/blob/master/LICENSE)

Python interpreter bindings for Deno.

## Example

Import any locally installed Python package, for example, `matplotlib`:

```ts
import { python } from "https://deno.land/x/python@0.2.0/mod.ts";

const np = python.import("numpy");
const plt = python.import("matplotlib.pyplot");

const xpoints = np.array([1, 8]);
const ypoints = np.array([3, 10]);

plt.plot(xpoints, ypoints);
plt.show();
```

When running, you **must** specify `--allow-ffi`, `--allow-env` and
`--unstable` flag. Alternatively, you may also just specify `-A`
instead of specific permissions since FFI effectively means all
permissions.

```shell
deno run -A --unstable <file>
```

## Documentation

Check out the docs
[here](https://doc.deno.land/https://deno.land/x/python@0.2.0/mod.ts).

## Python Installation

This module uses FFI to interface with the Python interpreter's C API. So you
must have an existing Python installation (with the shared library), which is
something like `python39.dll`, etc.

Python installed from Microsoft Store does not work, as it does not contain
shared library for interfacing with Python interpreter.

If the module fails to find Python, you can add the path to the Python in the
`DENO_PYTHON_PATH` environment variable.

## Maintainers

- DjDeveloper ([@DjDeveloperr](https://github.com/DjDeveloperr))
- Elias Sjögreen ([@eliassjogreen](https://github.com/eliassjogreen))

## Other

### Contribution

Pull request, issues and feedback are very welcome. Code style is formatted with
`deno fmt` and commit messages are done following Conventional Commits spec.

### Licence

Copyright 2021, DjDeveloperr.

Copyright 2022, the Denosaurs team. All rights reserved. MIT license.
