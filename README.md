# This is the officical website for Becho

- Fork The Repository
- Clone the Forked Repository
- Add Upstream to your forked repo
- 1. Open Terminal.
- 2. List the current configured remote repository for your fork.
  - \$ git remote -v
  * > origin https://github.com/YOUR_USERNAME/YOUR_FORK.git (fetch)
  * > origin https://github.com/YOUR_USERNAME/YOUR_FORK.git (push)
- 3. Specify a new remote upstream repository that will be synced with the fork.

  - git remote add upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git

- 4. Verify the new upstream repository you've specified for your fork.
  - \$ git remote -v
  * > origin https://github.com/YOUR_USERNAME/YOUR_FORK.git (fetch)
  * > origin https://github.com/YOUR_USERNAME/YOUR_FORK.git (push)
  * > upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git (fetch)
  * > upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git (push)
- Link : https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/configuring-a-remote-for-a-fork

- Run The follwing commands
  - npm start
  - npm insatall
  - npm runserver

* Formatting and Whitespace

* Formatting and whitespace issues are some of the more frustrating and subtle problems that many developers _ encounter when collaborating, especially cross-platform. It’s very easy for patches or other collaborated _ work to introduce subtle whitespace changes because editors silently introduce them, and if your files ever touch a Windows system, \* their line endings might be replaced. Git has a few configuration options to help with these issues.

core.autocrlf

- If you’re programming on Windows and working with people who are not (or vice-versa), you’ll probably run into line-ending issues at some point. This is because Windows uses both a carriage-return character and a linefeed character for newlines in its files, whereas Mac and Linux systems use only the linefeed character. This is a subtle but incredibly annoying fact of cross-platform work; many editors on Windows silently replace existing LF-style line endings with CRLF, or insert both line-ending characters when the user hits the enter key.

- Git can handle this by auto-converting CRLF line endings into LF when you add a file to the index, and vice versa when it checks out code onto your filesystem. You can turn on this functionality with the core.autocrlf setting. If you’re on a Windows machine, set it to true – this converts LF endings into CRLF when you check out code:

\$ git config --global core.autocrlf true

- If you’re on a Linux or Mac system that uses LF line endings, then you don’t want Git to automatically convert them when you check out files; however, if a file with CRLF endings accidentally gets introduced, then you may want Git to fix it. You can tell Git to convert CRLF to LF on commit but not the other way around by setting core.autocrlf to input:

\$ git config --global core.autocrlf input

- This setup should leave you with CRLF endings in Windows checkouts, but LF endings on Mac and Linux systems and in the repository.

- If you’re a Windows programmer doing a Windows-only project, then you can turn off this functionality, recording the carriage returns in the repository by setting the config value to false:

\$ git config --global core.autocrlf false