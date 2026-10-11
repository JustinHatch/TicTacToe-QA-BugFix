# Tic for Tot — Manual QA Bug Investigation

An existing Tic-Tac-Toe project demonstrating bug reproduction, test-case design, Jira tracking, and TestRail fix verification.

## Reset defect

The broken game clears the visible marks when Restart Playtime is clicked, but does not reset the internal board array. A previously occupied square therefore rejects input in the next game. The fixed version resets both the internal board and the visible cells.

- [Complete defect description and reproduction steps](BugReport.md)
- [Nine documented test scenarios](TestCases.md)
- [Broken game](broken_version/index.html)
- [Fixed game](fixed_version/index.html)
- [TestRail case and steps](screenshots/tik%20for%20tot%20test%20rail%20screenshot%20fixed%20date%201.png)
- [TestRail passed reset run](screenshots/tik%20for%20tot%20test%20rail%20fixed%20screenshot%202.png)
- [Jira task board](screenshots/TICKET~1.JPG)

Open the HTML files in a browser to compare them. AI assistance supported troubleshooting and the code correction; the QA work includes manual reproduction and verification. This is portfolio project experience, not professional QA employment.

## Repository contents

```text
broken_version/index.html
fixed_version/index.html
screenshots/               # Original Jira/TestRail evidence and game screenshot
BugReport.md
TestCases.md
README.md
```

Original screenshot and project dates are unchanged. Recorded test outcomes are historical results, not a newly executed full regression suite.
