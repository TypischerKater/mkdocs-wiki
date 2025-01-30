---
tags:
  - python
---

# Start Mkdocs Project

Clone project

Update your machine to be up to date
```bash
  sudo apt update && apt upgrade -y && reboot
```

- Go to project folder `mkdocs-wiki` where also the readme etc is
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

- now vor C:\.... should be `(venv)`

- start the dev server so you can see changes you make
```bash
  mkdocs serve
```

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.