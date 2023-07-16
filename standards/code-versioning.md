# Git Tagging & Releases

## What is Git Tagging?

-   [Tagging](https://git-scm.com/book/en/v2/Git-Basics-Tagging) is a simple, easy way to keep track of your code at a certain point in time. Some instances where this becomes useful are:

    -   Client-facing deliverables such as milestones, UAT, or production launch/release.
    -   Internal-facing code at a point that you or your team wants to demarcate as important.
    -   Versioning of your code (as a default, EngageAI follows SemVer).

## [SemVer](https://semver.org/) Basics:

-   Always have an up-to-date documented API (in our case, README.md for our projects or Wiki)
-   Increment your versions based on a **Major.Minor.Patch** format where:

    -   **Major** changes are breaking non-backwards compatible changes to your code base.
    -   **Minor** changes are new features or functionality that are still backwards-compatible.
    -   **Patch** changes are bug fixes or hotfixes that only address issues and don't introduce anything new.

    ##### Example:

    ![example version](./assets/qa-process/semver.png)
    In this instance:

    -   We are on the `8`th major version, so there've been 7 changes that have broken backward compatibility in the past.
    -   We are on the `2`nd minor version which means there have been two feature changes that have been made.
    -   After we did our second feature push, we have had `6` bugs that we have fixed in the meantime.
    -   If we build a new feature that does not break existing APIs, this number will be changed to `8.3.0`.

*   Releases should be unalterable and locked -- forever.
*   Initial development (so most of our lives) should be treated as 0.x.x so as to indicate that there is no release as of yet.

    -   Generally, any software with a major version of 0 should be treated as unstable.

## Why should EngageAI care?

This should be self-evident. More maintainable code makes our jobs easier! Tagging does the following things:

-   Provides markers for points in our development cycle such as releases, patches, hotfixes, etc.
-   Keeps in-development projects organized by allowing for pre-releases (ie. 0.1.0, 0.2.0) that can be mapped to specific milestones.
-   Allows for quicker set-up time for new developers being added to your project.
-   Helps us to avoid introducing major breaking changes unintentionally for enforcing the major/minor/patch methodology.

## How do I do it?

Glad you asked! Because of our reliance on Git and GitHub.com, we have some pretty awesome out of the box tools we can use to implement SemVer _right now_!
Let's go through our use cases:

### I need to create my project's first version

1. Get your code to a place you're happy with
   _i.e. no console.logs, errant code, everything works, etc._
2. Create a Git tag using `git tag v0.1.0` or `git tag -a v0.1.0`.
   _Your team will have to decide what minor version to start with if you've already begun development._
3. Push your tag to GitHub.com using `git push origin <YOUR-TAG-NAME>`
   _Note: < YOUR-TAG-NAME > would be replaced by `v0.1.0` in our above example and *must* match._
4. If this is a release (i.e. you are going to deploy this for the client to test, or it is an update to a production app that will go live) [create a release](https://help.github.com/en/articles/creating-releases) on `GitHub.com`.

### I need to increment my project's patch version

1. Be sure your hotfix or bugfix changes have been reviewed and approved by your project's lead developer.
2. Once the fix is approved and your Pull Request is merged, checkout to your base branch (develop or main, whatever you use as your source of truth) and pull your changes.
3. Create your tag using `git tag v0.1.1`, remembering to increment from the last patch version, but keeping the major and minor versions the same.
4. Push your tag to GitHub.com using `git push origin <YOUR-TAG-NAME>`
   _Note: < YOUR-TAG-NAME > would be replaced by `v0.1.1` in our above example and *must* match._

### I need to increment my project's minor version

1. Be sure your feature branch changes have been reviewed and approved by your project's lead developer.
2. Checkout to your base branch (develop or main, whatever you use as your source of truth) and pull your changes.
3. Create your tag using `git tag v0.2.0`, remembering to increment from the last minor version, keeping the major version the same and resetting the patch version to 0.
4. Push your tag to GitHub.com using `git push origin <YOUR-TAG-NAME>`
   _Note: < YOUR-TAG-NAME > would be replaced by `v0.2.0` in our above example and *must* match._

### I need to increment my project's major version

1. Be sure your reverse-incompatable, breaking changes have been reviewed and approved by your project's lead developer.
2. Make a plan for your rollout to users with your client and make sure your deployment follows that plan.
3. Checkout to your base branch (develop or main, whatever you use as your source of truth) and pull your changes.
4. Create your tag using `git tag v1.0.0`, remembering to increment from the last major version and resetting your minor and patch versions to 0.
5. Push your tag to GitHub.com using `git push origin <YOUR-TAG-NAME>`
   _Note: < YOUR-TAG-NAME > would be replaced by `v1.0.0` in our above example and *must* match._

### I need to create a Release

_Releases are useful for marking a client-facing milestones in your code's history. Your project lead should determine when and how often a tag should be marked as a release._

1. Make sure that your tag has been pushed to GitHub.
2. Click on `releases` on the code tab of your repository.
3. Click the button labelled `Draft a new release`.
4. Enter your tag's name (must be exact) into the input to target your desired tag.  
   _It is possible to target a branch's current state as your release, but this is *not* advisable._
5. Enter a title for your release that makes contextual sense for the release's contained changes.
6. Include any release notes that your team has deemed important or necessary for each release. Generally these notes _should_ include:

-   A brief summary of feature changes or hotfixes that are included.
-   Additional notes for users of the code that are pertinent for the code base.

7. If you want to, you can include a diff link (provided automatically by GitHub) to view the differences between any two tags in your code base. As long as you have two or more tags, this can be accomplished by including a standard markdown link with the following format:  
   **https: //github .com /shift3/ < your-repository-name > /compare/< original-tag-name >...< new-tag-name >**  
   \_example: https://github.com/filtpod/ifg/compare/v0.4.0...v0.5.0

### Resources

[Git Tagging Docs](https://git-scm.com/book/en/v2/Git-Basics-Tagging)
[SemVer Main Docs](https://semver.org/)  
[SemVer Breakdown](https://www.jvandemo.com/a-simple-guide-to-semantic-versioning/)  
[Convincing Argument for SemVer](https://www.sitepoint.com/semantic-versioning-why-you-should-using/)  
[Slides for Tagging at EngageAI](https://docs.google.com/presentation/d/1mZ35fZ7GhIBcCAPzeAXXAprcQZUv4WL-BELp9tEsFE8/edit?usp=sharing)
