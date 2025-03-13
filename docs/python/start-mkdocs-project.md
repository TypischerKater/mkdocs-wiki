---
tags:
  - python
---

# Start Mkdocs Project

Clone project

- Make sure that `mkdocs` is installed if not you can use `pip install mkdocs` to install the package
- Make also sure that `mkdocs-material` is installed if not you can use `pip install mkdocs-material` to install the package
- Next go to project folder `mkdocs-wiki` where also the readme etc is
- Create python virtual environment
```bash
python -m venv venv
```

- Activate virtual environment
```bash
cd venv/Scripts
```

```bash
activate
```

- now in the console C:\.... should be `(venv)`

- start the dev server so you can see changes you make but make sure that you are in the folder where the `mkdocs.yml` file is located
```bash
mkdocs serve
```

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.