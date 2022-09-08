styleguide-config
=======

![GitLab License](
https://img.shields.io/gitlab/license/vkolupaev/styleguide-config?color=informational
)
![GitLab tag (latest by SemVer)](
https://img.shields.io/gitlab/v/tag/vkolupaev/styleguide-config?label=styleguide-config
)
![Python](
https://img.shields.io/static/v1?label=Python&message=3.10&color=informational&logo=python&logoColor=white
)

## What is this repository?
A set of code style tool settings to enforce them in other projects.

## To whom and how can it be useful?
First of all, I made this repository for myself. I'm tired of bringing tool settings into consistency code styles in
different projects.

If you are also tired 😊, then use this repository as an example and modify it for yourself.

## Ok, how to use it?
### Manual use in `DEV` environment

Follow these steps:
1. Clone the repo to yourself or fork, then edit. Make it public or create a _token_, so that `nitpick` can download
   the settings.
2. The styles are in the `styleguide-configstyles` directory. Check them out and edit them for yourself. Documentation
   `nitpick` by styles is [here](https://nitpick.readthedocs.io/en/latest/styles.html).
3. In your other projects:
   1. Install the `nitpick` library. I do it with `poetry`, including in the `dev-dependencies` section, for example:
   ```toml
   [tool.poetry.dev-dependencies]
   nitpick = "^0.32.0"
   pre-commit = "^2.20.0"
   isort = "^5.10.1"
   black = "^22.8.0"
   mypy = "0.931"
   wemake-python-styleguide = "^0.16.1"
   bandit = "^1.7.4"
   ```
   2. Add a `tool.nitpick` section to `pyproject.toml`:
   ```toml
   [tool.nitpick]
   # Specify the address of your repo. If the repo is private, then specify with the token created in step 1.
   # The token can be passed through an environment variable so as not to shine in the code, see the documentation:
   # https://nitpick.readthedocs.io/en/latest/configuration.html#remote-style
   style = [
       "https://gitlab.com/vkolupaev/styleguide-config/-/raw/main/styles/nitpick-style.toml",
   ]

   # For the duration of the active style setting, I recommend specifying `never`. Then delete.
   # Documentation on caching settings: https://nitpick.readthedocs.io/en/latest/configuration.html#remote-style
   cache = "never"
   ```
   3. Use the CLI `nitpick` to check and match against uniform settings.
      1. Документация по CLI.
      2. Example
      ```bash
      nitpick check  # check everything
      nitpick fix  # fix everything

      nitpick check setup.cfg  # check only the specified file
      nitpick fix setup.cfg  # fix only the specified file
      ```

### Usage in CI pipeline
If you are a Team Lead and you manage several projects, and you do not conduct code review 100% PullRequests
(for example, delegate some of these tasks), then you can embed checking configuration files into the CI pipeline for
compliance with the standard.

To do this, consult with your DevOps Engineer.

## I have an error or have a question or idea💡. What to do?
There are two options:
1. Create an Issue and describe the situation:
   1. GitLab: [https://gitlab.com/vkolupaev/styleguide-config/-/issues](https://gitlab.com/vkolupaev/styleguide-config/-/issues)
   2. GitHub: [https://github.com/ViacheslavKolupaev/styleguide-config/issues](https://github.com/ViacheslavKolupaev/styleguide-config/issues)
2. Please feel free to write to me. My contacts are listed below 👇.

---

Copyright 2022 [Viacheslav Kolupaev](
https://vkolupaev.com/?utm_source=readme&utm_medium=link&utm_campaign=styleguide-config
).

[![website](
https://img.shields.io/static/v1?label=website&message=vkolupaev.com&color=blueviolet&style=for-the-badge&
)](https://vkolupaev.com/?utm_source=readme&utm_medium=badge&utm_campaign=styleguide-config)

[![LinkedIn](
https://img.shields.io/static/v1?label=LinkedIn&message=vkolupaev&color=informational&style=flat&logo=linkedin
)](https://www.linkedin.com/in/vkolupaev/)
[![Telegram](
https://img.shields.io/static/v1?label=Telegram&message=@vkolupaev&color=informational&style=flat&logo=telegram
)](https://t.me/vkolupaev/)
