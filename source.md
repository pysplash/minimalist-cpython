# Source Code Layout

For modules:

- `Lib/<module>.py`
- `Modules/_<module>module.c` (if there's also a C accelerator module)
- `Lib/test/test_<module>.py`
- `Doc/library/<module>.rst`

For extension-only modules, the typical layout is:

- `Modules/<module>module.c`
- `Lib/test/test_<module>.py`
- `Doc/library/<module>.rst`

For builtin types, the typical layout is:

- `Objects/<builtin>object.c`
- `Lib/test/test_<builtin>.py`
- `Doc/library/stdtypes.rst`

For builtin functions, the typical layout is:

- `Python/bltinmodule.c`
- `Lib/test/test_<builtin>.py`
- `Doc/library/functions.rst`

Some Exceptions:

- builtin type `int` is at `Objects/longobject.c`
- builtin type `str` is at `Objects/unicodeobject.c`
