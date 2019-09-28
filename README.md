# github-fix-reopened-tabs
A browser extension that fixes the broken behaviour of GitHub on reopened tabs

## Problem

When you 

1. open a GitHub issue (or Pull Request) in your browser
1. change something in the issue (for example add or remove some labels)
1. close the tab with <kbd>Ctrl</kbd> + <kbd>W</kbd>
1. then undo closing the tab with <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>T</kbd> 

it will load the issues as it was _before_ you changed the labels.

If this is a typical workflow for you (as is it for me when triaging hundreds of issues), this is super confusing and a frequent source of frustration.

These gifs illustrate the problem (Sorry, I couldn't find out how to record/add the key presses visually; you will probably also have to watch a few times until you understand where the animation starts and ends):

- Firefox:  
   ![github-bug-firefox](https://user-images.githubusercontent.com/183673/65816536-31cced80-e1fd-11e9-886a-e67b0b2ea9ea.gif)
- Chrome:   
   ![github-bug-chrome](https://user-images.githubusercontent.com/183673/65816538-398c9200-e1fd-11e9-8f19-cbd0cdf8a2d7.gif)
   
(The exact behavior may depend on your browser: In Chrome this will mostly only happen if you close the tabs _directly_ after making the changes. In Firefox you encounter this problem even if you wait for the changes to be properly reflected in the DOM.)

## Solution

This extension will try to track changes to a GitHub issue, then if a tab is reopened and it detects the "this is probably showing outdated information now" situation it reloads the page manually instead of letting the browser show an outdated version of it.

## TODO

All of it.

- [ ] Is this actually a browser or a GitHub problem?
- [ ] How to track "changes to an issue"?
- [ ] How to recognize "undo close tab"?
- [ ] Can an extension trigger a reload of a tab?
- [ ] Unwanted side effects?
