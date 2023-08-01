## API responses on the basis of *how* the Issue got closed
### Issue Closed using the 'Close Issue' button on Github

**Reference:** [Issue #7](https://github.com/KDwevedi/c4gt-docs/issues/7)    
**API Response:** [Issue #7 API Response](https://api.github.com/repos/KDwevedi/c4gt-docs/issues/7)    
**Closed By:**
```json
"closed_by": {
    "login": "KDwevedi",
    "id": 74085496,
    "node_id": "MDQ6VXNlcjc0MDg1NDk2",
    "avatar_url": "https://avatars.githubusercontent.com/u/74085496?v=4",
    "gravatar_id": "",
    "url": "https://api.github.com/users/KDwevedi",
    "html_url": "https://github.com/KDwevedi",
    "followers_url": "https://api.github.com/users/KDwevedi/followers",
    "following_url": "https://api.github.com/users/KDwevedi/following{/other_user}",
    "gists_url": "https://api.github.com/users/KDwevedi/gists{/gist_id}",
    "starred_url": "https://api.github.com/users/KDwevedi/starred{/owner}{/repo}",
    "subscriptions_url": "https://api.github.com/users/KDwevedi/subscriptions",
    "organizations_url": "https://api.github.com/users/KDwevedi/orgs",
    "repos_url": "https://api.github.com/users/KDwevedi/repos",
    "events_url": "https://api.github.com/users/KDwevedi/events{/privacy}",
    "received_events_url": "https://api.github.com/users/KDwevedi/received_events",
    "type": "User",
    "site_admin": false
  }
  ```
**[Timeline](https://api.github.com/repos/KDwevedi/c4gt-docs/issues/7/timeline):**
```json
[
  {
    "id": 9971875559,
    "node_id": "CE_lADOJ-2uL85tGt8gzwAAAAJSXr7n",
    "url": "https://api.github.com/repos/KDwevedi/c4gt-docs/issues/events/9971875559",
    "actor": {
      "login": "KDwevedi",
      "id": 74085496,
      "node_id": "MDQ6VXNlcjc0MDg1NDk2",
      "avatar_url": "https://avatars.githubusercontent.com/u/74085496?v=4",
      "gravatar_id": "",
      "url": "https://api.github.com/users/KDwevedi",
      "html_url": "https://github.com/KDwevedi",
      "followers_url": "https://api.github.com/users/KDwevedi/followers",
      "following_url": "https://api.github.com/users/KDwevedi/following{/other_user}",
      "gists_url": "https://api.github.com/users/KDwevedi/gists{/gist_id}",
      "starred_url": "https://api.github.com/users/KDwevedi/starred{/owner}{/repo}",
      "subscriptions_url": "https://api.github.com/users/KDwevedi/subscriptions",
      "organizations_url": "https://api.github.com/users/KDwevedi/orgs",
      "repos_url": "https://api.github.com/users/KDwevedi/repos",
      "events_url": "https://api.github.com/users/KDwevedi/events{/privacy}",
      "received_events_url": "https://api.github.com/users/KDwevedi/received_events",
      "type": "User",
      "site_admin": false
    },
    "event": "closed",
    "commit_id": null,
    "commit_url": null,
    "created_at": "2023-08-01T05:14:34Z",
    "state_reason": null,
    "performed_via_github_app": null
  }
]
```

### Issue closed by PR merger: Case 1
Issue closed automatically on PR merger. PR was linked using [keywords](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue#linking-a-pull-request-to-an-issue-using-a-keyword).    
**Reference Issue:** [Issue #8](https://github.com/KDwevedi/c4gt-docs/issues/8)    
**API Response:** [Issue #8 API Response](https://api.github.com/repos/KDwevedi/c4gt-docs/issues/8)    

**Closed By:**   
This section seems to be the user who *merged* the PR and not the user who *raised* the PR. [Reference Community Issue](https://api.github.com/repos/Code4GovTech/discord-bot/issues/6)    
```json
"closed_by": {
    "login": "KDwevedi",
    "id": 74085496,
    "node_id": "MDQ6VXNlcjc0MDg1NDk2",
    "avatar_url": "https://avatars.githubusercontent.com/u/74085496?v=4",
    "gravatar_id": "",
    "url": "https://api.github.com/users/KDwevedi",
    "html_url": "https://github.com/KDwevedi",
    "followers_url": "https://api.github.com/users/KDwevedi/followers",
    "following_url": "https://api.github.com/users/KDwevedi/following{/other_user}",
    "gists_url": "https://api.github.com/users/KDwevedi/gists{/gist_id}",
    "starred_url": "https://api.github.com/users/KDwevedi/starred{/owner}{/repo}",
    "subscriptions_url": "https://api.github.com/users/KDwevedi/subscriptions",
    "organizations_url": "https://api.github.com/users/KDwevedi/orgs",
    "repos_url": "https://api.github.com/users/KDwevedi/repos",
    "events_url": "https://api.github.com/users/KDwevedi/events{/privacy}",
    "received_events_url": "https://api.github.com/users/KDwevedi/received_events",
    "type": "User",
    "site_admin": false
  },
```
**[Timeline](https://api.github.com/repos/KDwevedi/c4gt-docs/issues/8/timeline):**   
A new relevant event 'cross-referenced' appears. Indicated Connection between PR-Issue.    
This *doesn't* appear in [events api response](https://api.github.com/repos/KDwevedi/c4gt-docs/issues/8/events) for the issue.    

Contains 'actor' data item. This is the user that initiated the connection from PR.    
If PR is linked by contributor this will be contributor. If PR is linked by maintainer or mentor or someone else this will be that person.    
Reference: [PR Linked by contributor](https://api.github.com/repos/Code4GovTech/website/issues/18/timeline) | [PR Linked by maintainer](https://api.github.com/repos/Code4GovTech/discord-bot/issues/6/timeline)    

**Actor:**
```json
"actor": {
      "login": "KDwevedi",
      "id": 74085496,
      "node_id": "MDQ6VXNlcjc0MDg1NDk2",
      "avatar_url": "https://avatars.githubusercontent.com/u/74085496?v=4",
      "gravatar_id": "",
      "url": "https://api.github.com/users/KDwevedi",
      "html_url": "https://github.com/KDwevedi",
      "followers_url": "https://api.github.com/users/KDwevedi/followers",
      "following_url": "https://api.github.com/users/KDwevedi/following{/other_user}",
      "gists_url": "https://api.github.com/users/KDwevedi/gists{/gist_id}",
      "starred_url": "https://api.github.com/users/KDwevedi/starred{/owner}{/repo}",
      "subscriptions_url": "https://api.github.com/users/KDwevedi/subscriptions",
      "organizations_url": "https://api.github.com/users/KDwevedi/orgs",
      "repos_url": "https://api.github.com/users/KDwevedi/repos",
      "events_url": "https://api.github.com/users/KDwevedi/events{/privacy}",
      "received_events_url": "https://api.github.com/users/KDwevedi/received_events",
      "type": "User",
      "site_admin": false
    }
```

Contains 'Source' data item.   
Contains information about the PR that was linked to the issue.   

**Source:**
```json
"source": {
      "type": "issue",
      "issue": {
        "url": "https://api.github.com/repos/KDwevedi/c4gt-docs/issues/12",
        "repository_url": "https://api.github.com/repos/KDwevedi/c4gt-docs",
        "labels_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/issues/12/labels{/name}",
        "comments_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/issues/12/comments",
        "events_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/issues/12/events",
        "html_url": "https://github.com/KDwevedi/c4gt-docs/pull/12",
        "id": 1830484002,
        "node_id": "PR_kwDOJ-2uL85W3kfQ",
        "number": 12,
        "title": "Update README.md",
        "user": {
          "login": "KDwevedi",
          "id": 74085496,
          "node_id": "MDQ6VXNlcjc0MDg1NDk2",
          "avatar_url": "https://avatars.githubusercontent.com/u/74085496?v=4",
          "gravatar_id": "",
          "url": "https://api.github.com/users/KDwevedi",
          "html_url": "https://github.com/KDwevedi",
          "followers_url": "https://api.github.com/users/KDwevedi/followers",
          "following_url": "https://api.github.com/users/KDwevedi/following{/other_user}",
          "gists_url": "https://api.github.com/users/KDwevedi/gists{/gist_id}",
          "starred_url": "https://api.github.com/users/KDwevedi/starred{/owner}{/repo}",
          "subscriptions_url": "https://api.github.com/users/KDwevedi/subscriptions",
          "organizations_url": "https://api.github.com/users/KDwevedi/orgs",
          "repos_url": "https://api.github.com/users/KDwevedi/repos",
          "events_url": "https://api.github.com/users/KDwevedi/events{/privacy}",
          "received_events_url": "https://api.github.com/users/KDwevedi/received_events",
          "type": "User",
          "site_admin": false
        },
        "labels": [

        ],
        "state": "closed",
        "locked": false,
        "assignee": null,
        "assignees": [

        ],
        "milestone": null,
        "comments": 0,
        "created_at": "2023-08-01T05:18:52Z",
        "updated_at": "2023-08-01T05:19:04Z",
        "closed_at": "2023-08-01T05:19:04Z",
        "author_association": "OWNER",
        "active_lock_reason": null,
        "draft": false,
        "repository": {
          "id": 669888047,
          "node_id": "R_kgDOJ-2uLw",
          "name": "c4gt-docs",
          "full_name": "KDwevedi/c4gt-docs",
          "private": false,
          "owner": {
            "login": "KDwevedi",
            "id": 74085496,
            "node_id": "MDQ6VXNlcjc0MDg1NDk2",
            "avatar_url": "https://avatars.githubusercontent.com/u/74085496?v=4",
            "gravatar_id": "",
            "url": "https://api.github.com/users/KDwevedi",
            "html_url": "https://github.com/KDwevedi",
            "followers_url": "https://api.github.com/users/KDwevedi/followers",
            "following_url": "https://api.github.com/users/KDwevedi/following{/other_user}",
            "gists_url": "https://api.github.com/users/KDwevedi/gists{/gist_id}",
            "starred_url": "https://api.github.com/users/KDwevedi/starred{/owner}{/repo}",
            "subscriptions_url": "https://api.github.com/users/KDwevedi/subscriptions",
            "organizations_url": "https://api.github.com/users/KDwevedi/orgs",
            "repos_url": "https://api.github.com/users/KDwevedi/repos",
            "events_url": "https://api.github.com/users/KDwevedi/events{/privacy}",
            "received_events_url": "https://api.github.com/users/KDwevedi/received_events",
            "type": "User",
            "site_admin": false
          },
          "html_url": "https://github.com/KDwevedi/c4gt-docs",
          "description": "Docs for C4GT. Will make these permanent using Samagra Docs template as soon as they're narrowed down.",
          "fork": false,
          "url": "https://api.github.com/repos/KDwevedi/c4gt-docs",
          "forks_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/forks",
          "keys_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/keys{/key_id}",
          "collaborators_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/collaborators{/collaborator}",
          "teams_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/teams",
          "hooks_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/hooks",
          "issue_events_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/issues/events{/number}",
          "events_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/events",
          "assignees_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/assignees{/user}",
          "branches_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/branches{/branch}",
          "tags_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/tags",
          "blobs_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/git/blobs{/sha}",
          "git_tags_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/git/tags{/sha}",
          "git_refs_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/git/refs{/sha}",
          "trees_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/git/trees{/sha}",
          "statuses_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/statuses/{sha}",
          "languages_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/languages",
          "stargazers_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/stargazers",
          "contributors_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/contributors",
          "subscribers_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/subscribers",
          "subscription_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/subscription",
          "commits_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/commits{/sha}",
          "git_commits_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/git/commits{/sha}",
          "comments_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/comments{/number}",
          "issue_comment_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/issues/comments{/number}",
          "contents_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/contents/{+path}",
          "compare_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/compare/{base}...{head}",
          "merges_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/merges",
          "archive_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/{archive_format}{/ref}",
          "downloads_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/downloads",
          "issues_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/issues{/number}",
          "pulls_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/pulls{/number}",
          "milestones_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/milestones{/number}",
          "notifications_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/notifications{?since,all,participating}",
          "labels_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/labels{/name}",
          "releases_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/releases{/id}",
          "deployments_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/deployments",
          "created_at": "2023-07-23T18:51:44Z",
          "updated_at": "2023-08-01T07:05:21Z",
          "pushed_at": "2023-08-01T06:27:25Z",
          "git_url": "git://github.com/KDwevedi/c4gt-docs.git",
          "ssh_url": "git@github.com:KDwevedi/c4gt-docs.git",
          "clone_url": "https://github.com/KDwevedi/c4gt-docs.git",
          "svn_url": "https://github.com/KDwevedi/c4gt-docs",
          "homepage": null,
          "size": 39,
          "stargazers_count": 0,
          "watchers_count": 0,
          "language": null,
          "has_issues": true,
          "has_projects": true,
          "has_downloads": true,
          "has_wiki": false,
          "has_pages": false,
          "has_discussions": false,
          "forks_count": 0,
          "mirror_url": null,
          "archived": false,
          "disabled": false,
          "open_issues_count": 4,
          "license": null,
          "allow_forking": true,
          "is_template": false,
          "web_commit_signoff_required": false,
          "topics": [

          ],
          "visibility": "public",
          "forks": 0,
          "open_issues": 4,
          "watchers": 0,
          "default_branch": "main"
        },
        "pull_request": {
          "url": "https://api.github.com/repos/KDwevedi/c4gt-docs/pulls/12",
          "html_url": "https://github.com/KDwevedi/c4gt-docs/pull/12",
          "diff_url": "https://github.com/KDwevedi/c4gt-docs/pull/12.diff",
          "patch_url": "https://github.com/KDwevedi/c4gt-docs/pull/12.patch",
          "merged_at": "2023-08-01T05:19:04Z"
        },
        "body": "fixes #8 ",
        "reactions": {
          "url": "https://api.github.com/repos/KDwevedi/c4gt-docs/issues/12/reactions",
          "total_count": 0,
          "+1": 0,
          "-1": 0,
          "laugh": 0,
          "hooray": 0,
          "confused": 0,
          "heart": 0,
          "rocket": 0,
          "eyes": 0
        },
        "timeline_url": "https://api.github.com/repos/KDwevedi/c4gt-docs/issues/12/timeline",
        "performed_via_github_app": null,
        "state_reason": null
      }
    },
```
### Issue CLosed by PR Merger: Case 2   
Closed by linking through the [development tab in the Pull Request sidebar](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue#manually-linking-a-pull-request-to-an-issue-using-the-pull-request-sidebar)    
**Reference:** [Issue #9](https://github.com/KDwevedi/c4gt-docs/issues/9)  
**API Reference:** [Issue #9 API Response](https://api.github.com/repos/KDwevedi/c4gt-docs/issues/9)  

API Response is similar to [case 1](https://github.com/KDwevedi/c4gt-docs/edit/main/tech%20docs/issueApiResponseReference.md#issue-closed-by-pr-merger:-case-1)


  
