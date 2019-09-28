# github-fix-reopened-tabs
A browser extension that fixes the broken behaviour of GitHub on reopened tabs

## Problem

When you 

1. open a GitHub issue (or Pull Request) in your browser
1. change something in the issue (for example add or remove some labels)
1. close the tab with <kbd>Ctrl</kbd> + <kbd>W</kbd>
1. then undo closing the tab with <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>T</kbd> 

it will load the issues as it was _before_ you changed the labels.

(The exact behavior depends on your browser: In Chrome this will only happen if you close the tabs _directly_ after making the changes. In Firefox you encounter this problem even if you wait for the changes to be properly reflected in the DOM.)

If this is a typical workflow for you (as is it for me when triaging hundreds of issues), this is super confusing and a frequent source of frustration.

## Solution

This extension will try to track changes to a GitHub issue, then if a tab is reopened and it detects the "this is probably showing outdated information now" situation it reloads the page manually instead of letting the browser show an outdated version of it.

## TODO

All of it.

- [ ] How to track "changes to an issue"?
- [ ] How to recognize "undo close tab"?
- [ ] Can an extension trigger a reload of a tab?
- [ ] Unwanted side effects?
