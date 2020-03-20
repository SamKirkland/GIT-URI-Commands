# GIT-URI-Commands

This project registers a URI command for git. Allowing you to run GIT commands from URI links.
Useful for triggering merges/commits without leaving your web browser.

##### Setup Steps
- Download the project as a zip
- Unzip the download
- Open `GIT-URI-Commands/CustomProtocol/bin/Release/`
- Shift right-click on `GitCommand.exe` and Run As Administrator
- This will install a custom URL handler for the GIT merge links
- Note: May need to setup a path for `git` in your environment variables if you don't have it setup already (reboot when done).
- You can now trigger any git command from a URI/URL
- Make sure you escape the url before running it (with encodeURIComponent or similar)


### Examples
###### Triggering GIT from javascript
```javascript
// note: the url must be encoded! Also notice no "git" is needed (the program will add this before running the command). Using "://" instead of ":" will break the command
window.location.href = `git-command:${encodeURIComponent(`clone https://github.com/SamKirkland/GIT-URI-Commands`)}`;
```

```html
<!-- note: the url must be encoded! Also notice no "git" is needed (the program will add this before running the command). Using "://" instead of ":" will break the command -->
<a href="git-command:clone%20https%3A%2F%2Fgithub.com%2FSamKirkland%2FGIT-URI-Commands">
    Clone this repo
</a>
```


##### Security notes
When installing please edit the source and whitelist all domains you trust to run this command.
