## Rules for `python`-projects

- Packaging
    - when using `poetry` as a packaging system (as hinted by the existence of a `pyproject.toml` or by request), make sure to prefix your commands with `poetry run` from within the folder where the `pyproject.toml` resides
    - when starting a bash command using `poetry`, make sure that you are not in an active `venv` - if you are, prefix with `deactive &&` to leave the `venv`
    - namespace packages: in case there are multiple packages within the same project that share some python namespaces, (e.g. each project have a structure like `src/anabrid/lucihub/X` which means they share the `anabrid.lucihub` package), do _NOT_ create `__init__.py` files within the shared namespace folders or you will inadvertendly break the structure!
