### About

This is a document management project for LaTeX.

---
### Architecture

-.
├─ README.md
└── template
    ├── Makefile
    └── src
        └── template.

---
### How to use

ex. working at `template` directory

- To generate a pdf file at `template/docs` dicretory, execute the below command
```
template$ make
```

- To clean `template` dicretory, execute the below command
```
template$ make clean
```

- To open a generated pdf file, execute the below command
```
template$ make run
```

