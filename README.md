# dotAstro12-contribute-to-astropy
conversation about contributing to Astropy at .Astronomy 12


## Barriers to conributing
- Lack of familiarity with testing, git workflow, etc
- Time
- How to set up local copy of astropy and local environment to get docs build, tests working, etc.

## Kelle's take on Astropy contribution
- is the project getting too big?
- are there alternatives, like to send the core committee a code snippet?
- community manager (not sure real title) was just hired
- numpy, matplotlib have smaller dev community - hired a small number of full-time people with their money
- almost all astropy contributors wear multiple hats

## astropy affiliated packages
- astropy core is now too big. for example cosmology, which is in there, should maybe be an affiliated package
- astropy-managed packages: photutils, specreduce, astroquery. important, but not completely whole-field (e.g. cosmologists do not use photutils). astropy project commits to maintaining these
- astropy-affiliated packages: e.g. dustextinction, anything that is astro-related and relies on astropy tools. goes through review process. looks at: does documentation exist, does testing exist, are astropy standard packages/libraries used?
- https://www.astropy.org/affiliated/

## How to actually do it
- pre-commit: automatically fixes style guidelines, but makes you check if syle conforms
- get used to workflow on git
- what about commenting? the more the better, but no strict requirements. no use repeating in words exactly what code obviously says. usually, comments are for telling future devs that something might have caveats
- look at open issues. choose appropriate tags for your expertise. look at *good first issue* tag
  
### steps
- fork the repo
- clone your fork
- checkout a new branch
- `pip install -e ."[test]"` to install dependencies for astropy, make an editable astropy install in this branch
- make edits
- commit
- submit PR
- see also [astropy development page](https://docs.astropy.org/en/latest/development/index.html)

## live demo of a PR - fixing a documentation bug
- `pip install -e .[test]` fails on zsh. `pip install -e ".[test]"` is better because it works on bash and zsh.
- some ten-person partner-coding happened to fix the docs
- run tests to check if anything went wrong. use tox, which creates one or more environments and then runs pytest within them. running all tests takes time
- simultaneously can build the docs: `tox -e build_docs` which also takes some time. difference between using tox and sphinx is that tox makes an env and then runs everything
- `git add -U`
- `git commit -m whatever` will first run pre-commit, if configured. pre-commit autostyles
- `git push origin branchname`
- submit the PR. could also create draft, which is publicly visible and gets a PR number, but does not notify anyone.

## other resources
- consider submitting to [Journal of Open-Source Software (JOSS)](https://joss.theoj.org/)
- [Google summer of code](https://summerofcode.withgoogle.com/)
- 
