## Conventions for `python`-projects

- Tools (use those unless otherwise requested)
    - `uv` as package manager
    - cheap code checkers: `black`, `ruff`, a linter, run before you declare you're finished and install them as pre-commit hook
- Packaging
    - when using `uv` as a packaging system (as hinted by the existence of a `pyproject.toml` or by request), make sure to prefix your commands with `uv run` from within the folder where the `pyproject.toml` resides
    - when starting a bash command using `uv`, make sure that you are not in an active `venv` - if you are, prefix with `deactive &&` to leave the `venv`
    - namespace packages: in case there are multiple packages within the same project that share some python namespaces, (e.g. each project have a structure like `src/anabrid/lucihub/X` which means they share the `anabrid.lucihub` package), do _NOT_ create `__init__.py` files within the shared namespace folders or you will inadvertendly break the structure!
- avoid complex, nested dictionaries and prefer `pydantic` types
    - benefits readability and error checking
- when using forward imports for type checking using `TYPE_CHECKING`, remember to import the latter from `__future__`