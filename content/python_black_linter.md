---
title: The Best Linter for Black in VS Code
image: /images/black_logo.png
imageMeta:
  attribution:
  attributionLink: https://raw.githubusercontent.com/psf/black/master/docs/_static/logo2-readme.png
featured: true
authors:
  - levi
date: 2020-03-20
tags:
  - python
  - vscode
---

Forgive the clickbait title. The truth is that any linter can be configured to work well with Black. So any linter when properly configured will be the "best" linter for Black on VS Code. But before I give you the settings for the linter I configured a bit of background.

When I discovered automatic code formatting last year, I immediately started using it. I quickly found that [Black](https://black.readthedocs.io/en/stable/) is by far my favorite of these formatters. The options that come with Black are very limited. The developers do this on purpose, to limit the variety in the different coding styles that might exist between individuals.

Standardizing everything will be useful in a large group of programmers. I use it partly because I see many styles for formatting when looking for help on the internet. My style developed into this amalgamation of what I had seen on the internet. After adopting Black for all of my code, I would frequently run across errors with the linter (all of them) on VS Code. This was annoying and nothing more. It was however annoying enough for me to track down what I could do to solve it.

After doing some searching I found some instructions on what configurations are need for flake8 to be compatible with Black. While I type my code, I will follow the recommendations of the linter I use. However, when I format the document using Black, many little errors will come up. After tracking down the configurations need to ignore this issue, I entered them into VS Code so I don't have this issue anymore.

You can change the settings through the Settings tab if you prefer, but I will not cover those instructions here. To enter the `settings.json` file press `ctrl+,` then select the open settings (JSON) icon in the upper right hand corner. Then enter the following into the file:

```JSON
    "python.linting.enabled": true,
    "python.linting.flake8Enabled": true,
    "python.linting.flake8Args": [
        "--ignore=E203",
        "--ignore=E266",
        "--ignore=E501",
        "--ignore=W503",
        "--max-line-length=88",
        "--select = B,C,E,F,W,T4,B9",
        "--max-complexity = 18"
    ],
```

Not much too it. Enjoy!