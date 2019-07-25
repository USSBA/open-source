# Checklist

Based of GSA's open-source policy [checklist][gsa-checklist] and CFPB's [checklist][cfpb-checklist].  Please note that many items on the checklist are for deployable software.  If your code is not intended to be deployed elsewhere, and you are open sourcing your code for other reasons, such as to meet transparency goals, then please use your best judgment on assessing whether that item on the checklist applies to your situation.

---
## Checklist for Opening Source Software

1. Remove Personally Identifiable Information (PII)
    - [ ] Use [Poirot][poirot] (an evolution of [Clouseau][clouseau]) to scan the whole history for patterns that may contain PII
    - [ ] Use [BFG-repo-cleaner][repo-cleaner] to remove any content that should not be made public
2. Establish Automated tools
    - [ ] Use __Continuous Integration (CI) Tools__ like Jenkins or CircleCI to automate checks. Have multiple tools automated:
      - [ ] Use a tool to _check for Dependency Vulnerabilities_: in a Rails project use Hakiri or [GitHub for gem vulnerabilities][github-vul]
      - [ ] Use a open source _static analysis_ tool: in Rails use Brakeman Gem
      - [ ] Use Poirot with a pattern to _prevent PII from being committed_.
      - [ ] Use a _Style Guide and Linter_: in Rails use Rubocop (style guide and linter).
      - [ ] Automated Tests
3. Include all the Required Documentation in the repository
    - [ ] Update or create the __ReadMe.md__ file to contain the open source sections
    - [ ] Update or add the __License__
    - [ ] Include the (validated) __Code.JSON__ with the information for the project at the root of the repository.
    - [ ] Proper __documentation__ to use and access the project or API
4. Additionally for Developing in the Open
    - [ ] Add the __Contributing.md__ file
    - [ ] Add the __Security Policy__ file or section to the ReadMe file
    - [ ] Organize the ReadMe with consistent sections
    - [ ] Add the __Code of Conduct__ file or section to the ReadMe file
    - [ ] Optional but recommended, add a __Changelog.md__ file.
    - [ ] Automated Tools should run on every Pull Request.
    - [ ] Configure GitHub Protected Branches on `master`:
      - [ ] Require Pull Request before merge
      - [ ] Require CI tests to pass before merge
      - [ ] Include administrators/owners in these requirements
      - [ ] Optional: Require at least 1 other Pull Request approval
5. Verify that Components or 3rd party libraries that the Project uses that have different licenses or are not open source, are properly scoped and isolated to allow the OSS code to be open.
6. Notify the Open Source Point of Contact for the Agency

Nice to Haves:
1. Do a full Code Review.
2. Establish tools to set up a development environment (to set up Poirot locally for example).
3. Include a Change-log file.

Recommendations:
1. A pre-release internal checklist is highly recommended procedure for development teams.
2. [SPDX website][spdx] has a list of multiple open-source licenses and their abbreviations.

[gsa-checklist]: https://github.com/GSA/open-source-policy/blob/master/open_source_checklist.md
[cfpb-checklist]: https://github.com/cfpb/open-source-checklist/blob/master/opensource-checklist.md
[github-vul]: https://github.com/blog/2470-introducing-security-alerts-on-github
[poirot]: https://github.com/emanuelfeld/poirot
[clouseau]: https://github.com/cfpb/clouseau
[repo-cleaner]: https://rtyley.github.io/bfg-repo-cleaner/
[spdx]: https://spdx.org/licenses/
