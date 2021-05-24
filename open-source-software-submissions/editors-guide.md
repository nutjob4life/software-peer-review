# Guide for Editors

## Get Started Checklist

Follow the checklist below when serving as an editor for a package submitted to
pyOpenSci for review.

#### 1. Tag the Submission & Ensure You Have Sufficient Information From The Author

Once you begin the review process as an editor:

* Tag the submission issue with the `2/seeking-reviewer(s)` tag.
* Check the comment submission by the author to ensure that mandatory parts of submission template are complete.
  - If elements are not commplete, direct authors toward filling in any missing pieces.

#### 2. Check the Package for Basic Infrastructure

- Make sure that the package contains a basic testing framework and CI setup required by PyOpenSci. This avoids additional and redundant reviewer time.
- Also skim the package for sufficient documentation, style, and basic linting

#### 3. Next, Add a Comment With the Editor Checks
Once the above is complete you are ready to add editor checks to the issue.

- Add a comment to the issue that contains a copy of the Editor Checks template (see below) filled out with your response to the checks that begin the review.
- In this comment you will add reviewers and the review deadline date once you have reviewers assigned (see below)

```markdown
## Editor checks:

- [ ] **Fit**: The package meets criteria for [fit](https://www.pyopensci.org/contributing-guide/open-source-software-peer-review/aims-and-scope.html#package-categories) and [overlap](https://www.pyopensci.org/contributing-guide/open-source-software-peer-review/aims-and-scope.html#package-overlap).
- [ ] **Automated tests:** Package has a testing suite and is tested via Travis-CI or another CI service.
- [ ] **License:** The package has an OSI accepted license
- [ ] **Repository:** The repository link resolves correctly
- [ ] **Archive** (JOSS only, may be post-review): The repository DOI resolves correctly
- [ ] **Version** (JOSS only, may be post-review): Does the release version given match the GitHub release (v1.0.0)?

---

## Editor comments

---

Reviewers:
Due date:
```

- Fill out the Editor Checks sections for `Fit`, `Automated Tests`, `License`, and `Repository`
- Check against policies for [package fit within identified categories for the pyOpenSci ecosystem](../open-source-software-peer-review/aims-and-scope.html#package-categories)
- Check against policies for [package overlap of functionality with other packages](../open-source-software-peer-review/aims-and-scope.html#package-overlap).

If the package does not fit the pyOpenSci scope and policies and needs to be
rejected, see [this section](#responding-to-out-of-scope-submissions) about how
to respond.

- `Archive` and `Version` within the editor checks for JOSS may be filled out at the end of the review. The JOSS component of the review happens last after all of the review on the pyOpenSci side is complete.


- If initial checks show major gaps, request changes before assigning reviewers.

#### 4. Identify Reviewers

- Within one week of completing the editor checks, identify two reviewers for the package (see sections below for additional guidance on finding and selecting reviewers).
- Once reviewers have been identified:
  - Modify the Editor Comments under Editor Checks to add reviewer names and assign due date (typically 2-3 week turnaround). Also add the reviewers to the initial top comment in the issue.

    - `Reviewers: Full Name  (@github_username) and Full Name (@github_username)`
    - `Due date: Date`
    - Include in your comment to the reviewers:
      - Link to the reviewer guide for reviewers
      - Link to the review template
  - Edit the original comment submitted by author to fill in the Editor and Reviewer Information:
    - `Editor: Full Name (@github_username)`
    - `Reviewer 1: Full Name (@github_username)`
    - `Reviewer 2: Full Name (@github_username)`
    - `Archive` and `Version accepted` are filled out at the end of the review.
  - Tag issue with `3/reviewer(s)-assigned` tag

### General Review guidelines

- For packages needing continuous integration on multiple platforms ([criteria in this section of the packaging chapter](../authoring/overview#continuous-integration)), make sure the package gets tested on multiple platforms (e.g. MAC, Windows, Linux).
- Wherever possible when asking for changes in the review process, direct authors to automatic tools and online resources.
  - If the package raises a new issue for pyOpenSci policy, create an issue on [pyOpenSci's governance repo](https://github.com/pyOpenSci/governance)

## Guidelines For Identifying Reviewers

### Tasks
- Use the [email template](../appendices/templates#review-request-template) if needed to invite reviewers.
    -  When inviting reviewers, include something like "if I don't hear from you in a week, I'll assume you are unable to review," so as to give a clear deadline when you'll move on to looking for someone else.

### Where to Look for Reviewers?

As a (guest) editor, use:
* the potential suggestions made by the submitter(s), (although submitters may have a narrow view of the types of expertise needed.  We suggest not using more than one of suggested reviewers).
* the authors of [pyOpenSci packages](https://github.com/pyOpenSci/).

When these sources of information are not enough:
* ping other editors for ideas.
* look for users of the package or of the data source/upstream service the package connects to (via their opening issues in the repository, starring it, citing it in papers, talking about it on Twitter).
* You can also search for authors/maintainers of related packages on [PyPI](https://pypi.org/search/).

#### Criteria for Choosing Reviewers

Here are criteria to keep in mind when choosing a reviewer. You might need to
piece this information together by searching `PyPI`, `Conda` / `Conda-forge` and
the potential reviewer’s GitHub page and general online presence (personal
website, Twitter).

* Has not reviewed a package for us within the last 6 months.
* Some package development experience.
* Some domain experience in the field of the package or data source.
* No [conflicts of interest](../open-source-software-peer-review/policies-and-guidelines.html#conflict-of-interest)

https://www.pyopensci.org/contributing-guide/open-source-software-peer-review/policies-and-guidelines.html#conflict-of-interest

      open-source-software-peer-review/policies-and-guidelines.html#conflict-of-interest.
* Try to balance your sense of the potential reviewer’s experience against the complexity of the package.
* **Diversity** - with two reviewers both shouldn’t be cis white males.
* Some evidence that they are interested in openness or Python community activities, although blind emailing is fine.

Each submission should be reviewed by _two_ package reviewers. Although it is
fine for one of them to have less package development experience and more domain
knowledge, the review should not be split in two.  Both reviewers need to review
the package comprehensively, though from their particular perspective.  In
general, at least one reviewer should have prior reviewing experience, and of
course inviting one new reviewer expands our pool of reviewers.

## Editor Responsibilities During Review:

-   Check in with reviewers and authors occasionally. Offer clarification and help as needed.
-   In general aim for 3 weeks for review, 2 weeks for subsequent changes, and 1 week for reviewer approval of changes.
-   Upon all reviews being submitted, change the review status tag to `4/review-in-awaiting-changes` to update the reminder bot.
-   If the author stops responding, refer to [the policies](peer_review_proc#review-process-guidelines) and/or ping the other editors in the Slack channel <*Not available publically yet*> for discussion. Importantly, if a reviewer was assigned to a closed issue, contact them when closing the issue to explain the decision, thank them once again for their work, and make a note in our database to assign them to a submission with high chances of smooth software review next time (e.g. a package author who has already submitted packages to us).
-   Upon changes being made, change the review status tag to `5/awaiting-reviewer-response`.

### Editor Responsibilities After Review:

Once the package has been accepted through the review process:

- Change the status tag of the issue to `6/approved`
- Update the top of the issue with the version of the package that was approved and the doi.

If the package was accepted by JOSS:

- Fill out `Archive` and `Version` for JOSS under Editor Checks comment.
- Fill out `Archive` and `Version accepted` in the original comment submitted by author.

- Then post the approval template below to the issue. This template asks the authors and reviewers to add themselves and the package that was approved to the pyOpenSci website.

```
----------------------------------------------
🎉 <package-name-here> has been approved by pyOpenSci! Thank you <maintainer-name-here> for submitting <package-name> and many thanks to <reviewer-names-here> for reviewing this package! 😸  

There are a few things left to do to wrap up this submission:
- [ ] Add the badge for pyOpenSci peer-review to the README.md of <package-name-here>. The badge should be `[![pyOpenSci](https://tinyurl.com/y22nb8up)](https://github.com/pyOpenSci/software-review/issues/issue-number)`
- [ ] Add <package-name> to the pyOpenSci website. <maintainer-name>, please open a pr to update [this file](https://github.com/pyOpenSci/pyopensci.github.io/blob/master/_data/packages.yml): to add your package and name to the list of contributors
- [ ] <reviewers-and-maintainers> if you have time and are open to being listed on our website, please add yourselves to [this file](https://github.com/pyOpenSci/pyopensci.github.io/blob/master/_data/contributors.yml) via a pr so we can list you on our website as contributors!

<IF JOSS SUBMISSION>
This package is going to move on to JOSS for review. I believe @arfon will ask you to implement the items below but let's let him chime in here first!
- [ ] Activate Zenodo watching the repo
- [ ] Tag and create a release so as to create a Zenodo version and DOI
- [ ] Submit to JOSS using the Zenodo DOI. We will tag it for expedited review.

<IF JOSS SUBMISSION/>

All -- if you have any feedback for us about the review process please feel free to share it here. We are always looking to improve our process and our documentation in the [contributing-guide](https://www.pyopensci.org/contributing-guide). We have also been updating our documentation to improve the process so all feedback is appreciated!
```

When all of the above steps are complete, you can close the software-review issue.

#### Optional - Move Package to PyOpenSci Organization (BETA)

rOpenSci packages often live in the rOpenSci organization. PyOpenSci is still
figuring out whether this model fits for the Python community. If an author is
interested in this option, consider doing the following:

-   If package will be migrated to `pyOpenSci`:
    -   Create a two-person team in pyOpenSci's "pyOpenSci" GitHub organization, named for the package, with yourself and the package author as members.
    -   Have the author transfer the repository to `pyOpenSci`
    -   Go to the repository settings in the "pyOpenSci" GitHub organization and give the author "Admin" access to the repository.
-   Ask author to:
    -  Change any needed links, such those for CI badges
    -  Add pyOpenSci badge: `[![pyOpenSci](https://tinyurl.com/y22nb8up)](link-to-issue)`.
    -   Re-activate CI services
        -  For Travis, activating the project in the pyOpenSci account should be sufficient
        -  For AppVeyor, tell the author to update the GitHub link in their badge, but do not transfer the project: AppVeyor projects should remain under the authors' account. The badge is `[![AppVeyor Build Status](https://ci.appveyor.com/api/projects/status/github/pyOpenSci/pkgname?branch=master&svg=true)](https://ci.appveyor.com/project/individualaccount/pkgname)`.
        -  For Codecov, the webhook may need to be reset by the author.
-   Add a "peer-reviewed" topic to the repository.