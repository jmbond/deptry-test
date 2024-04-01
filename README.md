# Testing [deptry][deptry]

[deptry][deptry] fails to parse notebooks using special notebook syntax and line continuation characters.

```bash
$ deptry -ddg dev .
Scanning 4 files...
Warning: Skipping processing of notebook-exclamation.ipynb because of the following error: "SyntaxError: invalid syntax. Got unexpected token '!' at byte offset 0".
Warning: Skipping processing of notebook-line-continuation.ipynb because of the following error: "SyntaxError: invalid syntax. Got unexpected token Newline at byte offset 9".
Warning: Skipping processing of notebook-percent.ipynb because of the following error: "SyntaxError: invalid syntax. Got unexpected token '%' at byte offset 19".

pyproject.toml: DEP002 'numpy' defined as a dependency but not used in the codebase
pyproject.toml: DEP002 'jupyter' defined as a dependency but not used in the codebase
Found 2 dependency issues.

For more information, see the documentation: https://deptry.com/
```

Use of line continuation character in regular `.py` file works fine, as shown in `line-continuation.py`.

## Setup

Using [uv][uv]:

```bash
uv venv
source .venv/bin/activate
uv pip install -r requirements-dev.txt
```

[deptry]: https://deptry.com/
[uv]: https://github.com/astral-sh/uv
