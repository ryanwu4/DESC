# Contributing to DESC

:+1::tada: First off, thanks for taking the time to contribute! :tada::+1:

The following is a set of guidelines for contributing to DESC
These are mostly guidelines, not rules. Use your best judgment, and feel free to propose changes to this document in a pull request.

#### Table Of Contents

[I don't want to read this whole thing, I just have a question!!!](#i-dont-want-to-read-this-whole-thing-i-just-have-a-question)

[How Can I Contribute?](#how-can-i-contribute)
  * [Reporting Bugs](#reporting-bugs)
  * [Suggesting Enhancements](#suggesting-enhancements)
  * [Your First Code Contribution](#your-first-code-contribution)
  * [Pull Requests](#pull-requests)

[Styleguides](#styleguides)
  * [Git Commit Messages](#git-commit-messages)
  * [Python](#python-styleguide)
* [Documentation Styleguide](#documentation-styleguide)

[Additional Notes](#additional-notes)
  * [Issue and Pull Request Labels](#issue-and-pull-request-labels)


## I don't want to read this whole thing I just have a question!!!

> **Note:** Please don't file an issue to ask a question.

If you just want to ask a question, the simplest method for now is to just contact the authors (Daniel Dudt & Rory Conlin) directly (If you're reading this, you probably know who we are and how to get in touch). 

As the user base expands and more people start using and contributing to the code, we may set up some sort of user group Slack or Discord or other forum for questions and discussion among users/developers.


## How Can I Contribute?

### Reporting Bugs

#### How Do I Submit A (Good) Bug Report?

Bugs are tracked as [GitHub issues](https://github.com/DESC/issues/).

Explain the problem and include additional details to help maintainers reproduce the problem:

* **Use a clear and descriptive title** for the issue to identify the problem.
* **Describe the exact steps which reproduce the problem** in as many details as possible. When listing steps, **don't just say what you did, but explain how you did it**. 
* **Provide specific examples to demonstrate the steps**. Include links to files or copy/pasteable snippets, which you use in those examples. If you're providing snippets in the issue, use [Markdown code blocks](https://help.github.com/articles/markdown-basics/#multiple-lines).
* **Describe the behavior you observed after following the steps** and point out what exactly is the problem with that behavior.
* **Explain which behavior you expected to see instead and why.**
* **Include plots** of results that you believe to be wrong.
* **If you're reporting that DESC crashed**, include the python stack trace and full error message. Include the stack trace in the issue in a [code block](https://help.github.com/articles/markdown-basics/#multiple-lines), a [file attachment](https://help.github.com/articles/file-attachments-on-issues-and-pull-requests/), or put it in a [gist](https://gist.github.com/) and provide link to that gist.

Provide more context by answering these questions:

* **Did the problem start happening recently** (e.g. after updating to a new version of DESC) or was this always a problem?
* If the problem started happening recently, **can you reproduce the problem in an older version of DESC?** What's the most recent version in which the problem doesn't happen? 
* **Can you reliably reproduce the issue?** If not, provide details about how often the problem happens and under which conditions it normally happens.

Include details about your configuration and environment:

* **Which version of DESC are you using?** 
* **What's the name and version of the OS you're using**?
* **Are you running DESC in a virtual machine?** If so, which VM software are you using and which operating systems and versions are used for the host and the guest?
* **Are you running DESC locally or on a cluster?** If so, which cluster, with which modules loaded?
* **What hardware are you running on?** Which CPU, GPU, RAM, etc. If on a cluster, what resources are you allocating?

### Suggesting Enhancements

This section guides you through submitting an enhancement suggestion for DESC, including completely new features and minor improvements to existing functionality. 

Before creating enhancement suggestions, please check [this list](#before-submitting-an-enhancement-suggestion) as you might find out that you don't need to create one. When you are creating an enhancement suggestion, please [include as many details as possible](#how-do-i-submit-a-good-enhancement-suggestion), including the steps that you imagine you would take if the feature you're requesting existed.

#### Before Submitting An Enhancement Suggestion

* **Check the [documentation](https://desc-docs.readthedocs.io/en/latest/)** for tips — you might discover that the enhancement is already available. 
* **Perform a [cursory search](https://github.com/ddudt/DESC/issues?q=is%3Aopen+is%3Aissue+label%3Aenhancement)** to see if the enhancement has already been suggested. If it has, add a comment to the existing issue instead of opening a new one.

#### How Do I Submit A (Good) Enhancement Suggestion?

Enhancement suggestions are tracked as [GitHub issues](https://guides.github.com/features/issues/). After you've followed the above steps and verified that an issue does not already exist, create an issue and provide the following information:

* **Use a clear and descriptive title** for the issue to identify the suggestion.
* **Provide a step-by-step description of the suggested enhancement** in as many details as possible.
* **Provide specific examples to demonstrate the steps**. Include copy/pasteable snippets which you use in those examples, as [Markdown code blocks](https://help.github.com/articles/markdown-basics/#multiple-lines).
* **Describe the current behavior** and **explain which behavior you expected to see instead** and why.
* **Explain why this enhancement would be useful** to other users.
* **Provide references** (if relevant) to papers that discuss the physics behind the enhancement, or describe the enhancement in some way.

### Your First Code Contribution

Unsure where to begin contributing to Atom? You can start by looking through these `good first issue` and `help wanted` issues:

* [Good first issues](https://github.com/ddudt/DESC/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22) - issues which should only require a few lines of code, and a test or two.
* [Help wanted issues](https://github.com/ddudt/DESC/issues?q=is%3Aopen+is%3Aissue+label%3A%22help+wanted%22) - issues which should be a bit more involved than beginner issues.


## Styleguides

### Python Styleguide

* [Follow the PEP8 format](https://www.python.org/dev/peps/pep-0008/)
* Consider an automated linter such as [autopep8](https://pypi.org/project/autopep8/)
* **Readability** and **usability** are more important than speed 99% of the time. 
* If it takes more than 30 seconds to understand what a line or block of code is doing, include a comment summarizing what it does.
* If a function has more than ~5 inputs and/or return values, consider packaging them in a dictionary or custom class.
* Make things modular. Focus on small functions that [do one thing and do it well](https://en.wikipedia.org/wiki/Unix_philosophy#Origin), and then combine them together. Don't try to shove everything into a single function.
* *It's not Fortran*! You are not limited to 6 character variable names. Please no variables or functions like ``ma00ab`` or ``psifac``. Make names descriptive and clear. If the name and meaning of a variable is not immediately apparent, the name is probably wrong.
* Sometimes, a shorter, less descriptive name may make the code more readable. If you want to use an abbreviation or shorthand, include a comment with the keyword ``notation:`` explaining the notation at the beginning of the function or method explaining it, eg ``# notation: v = vartheta, straight field line poloidal angle in radians``.

#### ``jnp`` vs ``np``

DESC makes heavy use of the JAX library for accelerating code through JIT compiling and automatic differentiation. JAX has a submodule, ``jax.numpy``, commonly abbreviated as ``jnp`` which offers an API almost identical to ``numpy``. 

* If the function will ever be used for optimization (ie, called as part of an objective function), use ``jnp``.
* Similarly, if the function will need to be called multiple times and could benefit from JIT compiling, use ``jnp`` and ``jit``. However, in general it is best to only ``jit`` the outermost function, not each subfunction individually.
* If the function will ever need to be differentiated through, use ``jnp`` and ``jacfwd``, ``jacrev``, or ``grad``.
* If you are certain it will only ever be used during initialization or post processing (ie plotting), feel free to use ``np``, as it can be slightly faster without JIT compilation, and has fewer tricks necessary to make it work as expected.
* If in doubt, ``jnp`` is usually a safe bet.
* ``jax.numpy`` is *almost* a drop in replacement for ``numpy``, but there are some [subtle and important differences](https://jax.readthedocs.io/en/latest/notebooks/Common_Gotchas_in_JAX.html). 


### [Git Commit Messages](https://chris.beams.io/posts/git-commit/)

* Separate subject line from body with a single blank line.
* Limit the subject line to 50 characters or less, and wrap body lines at 72 characters.
* Capitalize the subject line.
* Use the present tense ("Add feature" not "Added feature") and the imperative mood ("Fix issue..." not "Fixes issue...") in the subject line.
* Reference issues and pull requests liberally in the body, including specific issue numbers. If the commit resolves an issue, note that at the bottom like ``Resolves: #123``.
* Explain *what* and *why* vs *how*. Leave implementation details in the code. The commit message should be about what was changed and why.


### Documentation Styleguide

* Use [SphinxDoc](https://www.sphinx-doc.org/en/master/index.html).
* Use [Google Style Docstrings](https://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html).
* Use [reStructuredText](https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html).