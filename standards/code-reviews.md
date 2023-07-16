# Code Reviews

### The purposes of code review at EngageAI (and in the industry generally) are:

1. Teachability:
   - They help you remain teachable
   - They allow us to learn from each other's experience. What developer _doesn't_ want to keep learning?
2. Catch Bugs:
   - They catch potential bugs from being integrated into the main code base
   - They ensure code quality and veracity
3. Improve Code:
   - Improve your code base by having another set of eyes on it
   - Catch security vulnerabilities that you may not have known about
   - Give more developers the ability to move between projects without the initial shock of not knowing _anything_ about the code

## Process

### Author

- At EngageAI we have a simple code review process

1. Before you create your Pull Request or tag anyone in anything, double check that you're ready

   Pre-PR checklist:

   - [ ] Test the specific code you're submitting
   - [ ] Use a linter (esLint is probably going to be the standard) to take care of whitespace and styling
   - [ ] Remove your console references and debuggers
   - [ ] Make sure your code changes are under 500 lines of code (break it up into more than 1 PR if it exceeds this)
   - [ ] Your PR should be based from the development branch, and not from other open PRs. If you MUST have stair-stepped PRs for a valid reason, please include justification in the PR and reference to the PRs which this new PR depends on.

2. Submit your pull request and tag potential reviewers. Always include the pr-team as potential reviewers.

   - "PR Team" is a list comprised of the developer team and when the PR is submitted the pr-team will then be replaced by 3 auto selected developers from that list.

     - There are also stack specific teams (ie. devs-wordpress, devs-react, etc.) and when these groups are selected to review the PR 2 developers from these lists will be selected.

   - The purpose of the pr-team:

     - To train developers to review code that they may not be completely comfortable with, yet can increase their breadth of understanding and encourages knowledge sharing amongst colleagues.

     - The PR Reviews are just as valuable as a learning opportunity for the reviewer as they are for the reviewee.

     - Automatic assignments balance the workload evenly across the whole team so everyone gets a chance to be a reviewer and a reviewee.

     - Pending PR reviews show up on the #bwtc-code-review Slack channel as a notification and reminder. This has helped us develop a quick turn-around on reviews.

   - Our standard code review process only requires a visual inspection of code. It is not necessary to pull down and run/test the code. That said, project teams can add their own functional review process within the team in addition to the standard cross-team visual review.

   - If you're assigned to a PR in which you are uncomfortable or unable to approve or request changes, that is not a problem. It is completely acceptable to provide a comment-only review. Provide any feedback you can and then **make sure to let the author know** you are unable to approve so that they can request additional reviewers.

3. Add comments when you create the PR that explain its scope, purpose, and any quirky things that you had to do to the code to make it work. Explain as much as possible in these comments to let the reviewer know about the PR. If you don't want it merged by a project maintainer, add a `DO NOT MERGE` label to the PR before it is reviewed.

4. If you receive a blocked review, fix up the issues and push the changes to your branch. Let the reviewer know when you have submitted the fix. Remember, we all make mistakes, and we all have room to grow. This is an opportunity to learn.

### Reviewer

1. Review any PRs you are tagged in immediately if possible

   - Here are some general guidelines to help you in your review

     - Use GitHub's Review dropdown framework and add your comments inline in the code

     - Limit your review time to half an hour (if the PR takes longer than that to review, suggest to the author that they break it up)

     - If you are part of the dev team for the project, your team may decide to have members pull code and test the app as part of the review. If you are not part of the dev team for the project, there is no requirement to actually test the code, just visually inspect it.

     - Don’t block the PR unless there is a legitimate bug

     - Frame your feedback as requests, not commands and be kind but direct (avoid using personal pronouns i.e. “Your code sucks…” “My code worked before you messed it up…”)

     - Provide code examples, references, links, etc when applicable

     - Don’t forget to compliment the submitter on good stuff, too!

2. Mark your review as one of the following:

   - `Request Changes`: If there are bugs in the code or something unacceptable being introduced to the code base (swearing in comments, console references and debuggers, etc.), you should block the PR and leave detailed comments as to why. If you block a PR and the author resubmits changes, get to them as quickly as you can and approve the PR once it's addressed.
   - `Approve`: If the code looks good and you have no questions/concerns, or if the author has submitted fixes to a blocking PR, mark it as approved.
   - `Comment`: If you have comments/concerns but you are not blocking the author (no bugs) then mark the review as comment and leave your comments. Let the author know that they can merge if they don't want to address your concerns.

3. If you are a maintainer for the project you can Squash & Merge or just Merge the PR and delete the compare branch once it is approved. If you are not a maintainer for the project, **DO NOT MERGE THE PR**. Leave it for the author or maintainers.

## Results

We have already had lots of success catching errors and bugs, as well as teaching each other what we know and sharing that knowledge in a way that normally doesn't happen. If you have a success story you have experienced, please submit a PR to this .md doc with your experience so you can share it!
Remember, this is a standard, so it isn't optional. _Never_ close your own Pull Requests.

## Resources

[Be a Human in your Code Reviews](https://mtlynch.io/human-code-reviews-1/)

[Lessons learned from former Google Code Reviewers](https://blog.fullstory.com/what-we-learned-from-google-code-reviews-arent-just-for-catching-bugs/)

[How to become a better code reviewer](https://blog.asana.com/2016/12/7-ways-to-uplevel-your-code-review-skills/)

[Digital Ocean's Effective Code Review Tips](https://blog.digitalocean.com/how-to-conduct-effective-code-reviews/)

[Corey Shuman's Dev Connect on Code Review](https://playback.lifesize.com/#/publicvideo/9a9229d2-22b1-40db-9e8e-26308225128d?vcpubtoken=910e3bbe-cc9e-489d-b844-afe87baaccaa)

[Google 'Speed of Code Reviews' Article](https://google.github.io/eng-practices/review/reviewer/speed.html)
