# Acceptance Testing

## What is Acceptance Testing

- At EngageAI, Acceptance Testing is testing to simulate real world end user scenarios. It is primarily handled by the QA team, who test the project from the same perspective as a user. They test on staging and production environments (not local ones), and without the inside and technical perspective of the developers who built the project.

## Purpose

- Writing Acceptance Tests lets the developer review their work. It can be very helpful in confirming that features are complete and that all edge cases are handled when describing what to do to a tester.
- Acceptance testing helps find problems that the developer might not have experienced: issues coming from different hardware/environments, or a tester performing an action in a different way than the developers. Developers can get too close to their work and not approach their product the same way an end user does.
- Acceptance testing saves money, time, and frustration. It is better to find issues from someone who can explain and demonstrate how they caused it, rather than from an upset client. It's also easier to fix an issue earlier in the development timeframe than later when potentially more functionality is built on top of the problem.

## How to create an Acceptance Test

- Setup info - the tester needs to know where and how to perform a test. They will need a website URL/instructions on what to download, instructions on how to make an account or be provided credentials. They also need to know if they have to test with specific hardware, software, web browsers, etc.
- A list of steps to perform the tests. This can be centralized in a primary GitHub issue with the steps given in a codeblock showing raw markdown that the tester can paste into their own issue. This allows the developer to write the steps in one spot, and each tester can create their own copy.
- The steps given by the developer should cover the minimum amount of functionality that the tester needs to test. Testers should try to find issues and bugs beyond the listed instructions. The instructions are a starting point and give the tester an idea of how the feature should work.
- Here is a snippet of an example test:

___

## DESCRIPTION

Ultra-Gro is an app for the internal use of Ultra-Gro sales. The app allows for employees to:

- View sales orders information
- Create sales reports
- Automatically generate sales order reports and delivery reports
- Archive orders
- Export sales order information to C21 (accounting software)
- Obtain signatures for sales order reports and delivery reports
- Import customers from a CSV collection that resides on the server (from C21)
- Generate sales proposals to pitch to customers

## ENVIRONMENT

To test the current build of Ultra-Gro, go to ultra-gro.shift3sandbox.com and log in with the credentials listed.

## CREDENTIALS

When testing on the staging server, there will be credentials available to you for each account:

FORMAT: `<account_name>`:`<sales_permission_level>`:`<proposal_permission_level>`

- `ug_admin`:`admin`:`none`
- `ug_dispatch`:`dispatch`:`none`
- `ug_sales_rep`:`sales-rep`:`none`
- `ug_view_only`:`view-only`:`none`
- `ug_proposal_user`:`view-only`:`proposal-user`
- `ug_proposal_user_2`:`view-only`:`proposal-user`
- `ug_proposal_admin`:`view-only`:`proposal-admin`
- `ug_inactive`:`none`:`none`

Ask Corey Shuman or Stephen Tuggy for the password.

## ACCEPTANCE

### Login

- [ ] After login, user is directed to `/sales_queue`
- [ ] Verify that `ug_inactive` is unable to log in and is informed that their account is inactive

___

- The QA person will create their own issue, blank to start, which they will not assign.
- The developer will assign the issue back to the QA tester with a link to the central issue where they can get the tests and begin testing.
- The QA tester will update the issue (original issue, not in a comment) with the acceptance tests from the primary issue.
- This allows the QA tester to be able to edit the QA tests (checkboxes) in the body of the issue. Using checkboxes in the body of the issue will update the overall issue progress. This helps developers and PMs get a higher level view of how testing is coming along.
- Additional issues/bugs/comments/dialog from the QA tester can go into comments below.
- Each QA tester should have their own issue to keep the conversations separate.
- The developers are responsible for figuring out how to map QA results to separate GitHub issues, and finding the appropriate repo/dev (e.g. the QA tester is doing acceptance testing in the front end repo and the issue stems from the API repo).
- Right now, we will experiment with having a single QA acceptance test issue per tester, updating the issue with new tests. We might break them up into multiple issues as we test this system.

## When to create an Acceptance Test

- Acceptance Tests must be written any time you want QA to review. A developer can choose when they want to hand off for test. Once the Acceptance Tests are written, PMs will schedule QA. QA should be minimally done ahead of the project's UAT milestone.

### Requirements to Schedule QA Time

- Websites must be running on a sandbox which the QA tester can access.
- Apps must be available to download via Testflight or Google Play.
- Acceptance Tests must be written.
- The development team should have already performed internal testing.
