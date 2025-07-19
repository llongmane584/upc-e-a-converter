# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## GitHub repository information
- Please reference the `.git/config` file to retrieve the repository URL from the `[remote "origin"]` section
- You can verify the remote URL using the `git config --get remote.origin.url` command
- When repository basic information is needed, please check `.git/config` first

## Commands

## GitHub Issues Management

### Viewing Issues
- List all issues: `gh issue list`
- View specific issue: `gh issue view <issue-number>`
- List issues with filters: `gh issue list --state open --assignee @me`

### Creating and Editing Issues
- Create new issue: `gh issue create --title "Title" --body "Description"`
- Edit existing issue: `gh issue edit <issue-number> --title "New Title" --body "New Description"`
- Add labels: `gh issue edit <issue-number> --add-label "bug,enhancement"`
- Assign issue: `gh issue edit <issue-number> --add-assignee "username"`
- Close issue: `gh issue close <issue-number>`
- Reopen issue: `gh issue reopen <issue-number>`

### Required Tools
- Ensure GitHub CLI (`gh`) is installed and authenticated
- Use `gh auth status` to verify authentication
- When working with issues, always specify issue numbers clearly

# Development Workflow (Issue-based)

- Planning: Create improvement plan and discuss approach
- Documentation: Once approved, add detailed implementation plan as comment to the issue (`gh issue comment`)
  - ** clearly marked as Claude Code generated with text `🤖 Generated with [Claude Code]`
- Branching: Create appropriately named feature branch
- Implementation: Write code following project standards
- Testing: Validate functionality in .venv environment
- Integration: Commit, push, and create pull request for review

### Issue Workflow Commands
- Comment on issue: `gh issue comment <issue-number> --body "Comment text"`
- Link to PR: `gh issue edit <issue-number> --add-label "linked-pr"`
- Set milestone: `gh issue edit <issue-number> --milestone "v1.0"`
