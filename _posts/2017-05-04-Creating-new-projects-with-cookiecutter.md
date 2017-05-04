---
layout: post
title: Creating new projects using cookiecutter
categories: data
tags: random

---


Creating new projects using cookiecutter
===

[*boilerplate*](http://whatis.techtarget.com/definition/boilerplate):

>In information technology, a boilerplate is a unit of writing that can be reused over and over without change. By extension, the idea is sometimes applied to reusable programming as in "boilerplate code."

`cookiecutter` is a tool that allows a new project to be easily created using an existing *boilerplate* source code project template. 
These templates consist of the standard directory tree and mandatory files. 
They can be stored in public git repos to be quickly called when needed.


Installing cookiecutter
---

Assuming `python` and `pip` are installed, [install cookiecutter](https://cookiecutter.readthedocs.io/en/latest/installation.html) by running

```
pip install --user cookiecutter
```

Start a new project from a [template](https://github.com/kragniz/cookiecutter-pypackage-minimal):

```
cookiecutter https://github.com/kragniz/cookiecutter-pypackage-minimal
```


Check the [list of python templates](https://cookiecutter.readthedocs.io/en/latest/readme.html#python)



Creating a new template
---

Follow the tutorial at
<http://cookiecutter.readthedocs.io/en/latest/first_steps.html>.

