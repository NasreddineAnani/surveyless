---
title: surveyless
subtitle: Build, run, and analyze simple serverless surveys
mode: OPEN
---

# :v: surveyless

https://surveyless.chrisrzhou.io

Build, run, and analyze simple serverless surveys.

Less servers.

Less setup.

Less costs.

Less complexity.

Less headaches.

![Logo](/src/images/Octocat.png)
Format: ![Alt Text](url)

## TODO

- explore markdown rendering for question description
- render question text as markdown
- work on tooltip
- local storage and hydrate state and reset browser cache

## Overview

### Ruthlessly simple

Skip the unneccessary paid features and complexity in various survey applications, and jump straight to building out a survey with basic features. **No accounts**, _keys_, ~~signups~~ or setup is required. Analyze results immediately once survey is closed.

### Fast and Reliable

Surveys are served blazingly fast over Netlify CDNs. There are no server components, and therefore no downtime when collecting responses or visualizing results.

### Atomic and automated workflow

The git repo is the single source of truth for creating surveys, storing responses and analyzing results. Automated builds are triggered when survey is created or closed. Rinse and repeat for future surveys.

## Setup

1. Click the `Deploy to Netlify` button to deploy an instance of `simple-survey` on Netlify and Github.
2. Create your survey in the admin interface.
3. You can save your work and continue working until you are ready to launch the survey. (Saving your survey is basically sending a PR to master and updating the `survey-config.json` file)
4. You can launch the survey publicly (anyone with a link can take the survey), or to a closed group of people (anyone with a valid link can take the survey).
5. Authorized people can respond to the survey and responses will be collected in the `responses` branch of the Git repo.
6. Close the survey to merge the `responses` branch back into master.
7. Analyze survey results with simple visualizations and tools.

Note: At any time, you can edit the `survey-config.json` file to directly change various settings of the survey that are synced and set by the UI.

## Question Types

- Single (Likert, Single)
  - Radio
  - Dropdown
- Multiple Choice
  - Checkbox
- Comment
- Scale
  - Star Rating
  - Slider
- Ranking
- Matrix

Support OPTIONAL "Other" option or "Additional Comments" for valid question types. All questions with options should have an option_score attached to it (for computing favorability).

Figure out a way to handle triggers (e.g. answering a certain value in one question triggers displaying/hiding another question). Figure out a way to store metadata or macros (e.g. parametrizing a question based on some input provided)

## TODO: Draft mode

- Navbar (surveymode, previewmode, question scroll-links)
- Edit/Create questions in draft mode
- Create choice_sets
- testmode (prepopulate data for various question types and preview, run validators)
- save and load from localstorage
- clear localstorage ('reset')
- save redux state to `survey.json` after validators pass
- hookup and merge PR when changes are 'committed' on UI.
- Find a way to set up and define panel (to measure participation rate or provide filterable dimensions in Results view)

## TODO: Survey mode

- next/back page
- submit survey
- save and load from localstorage
- clear localstorage ('reset')
- save redux state to `survey.json` after validators pass
- hookup and merge PR when changes are 'committed' on UI.

## TODO: Landing page

- correctly reads state from `survey.json` to render correct survey info (e.g link to survey or a 'survey closed/pending' message)

## TODO: Results page

- After `responses.json` is merged, render presentation/dashboard of results based on question types.

## Challenges

- Auto save using browser history. We don't have a server to handle saves, so we want to think how to avoid people losing their work.
- In `Setup 4.`, It is easy to have anyone take the survey, but we want to think of how closed group of people can take the survey. Unique survey URLs with authorized hashes could be an option, but the code to check for these hashes have to be made private. We could simply turn the repo into a private repo and that could solve the problem, but ideally we should find a way to do this without the need to make the repo private.

-

## Testing Markdown

# This is an <h1> tag

## This is an <h2> tag

###### This is an <h6> tag

_This text will be italic_
_This will also be italic_

**This text will be bold**
**This will also be bold**

_You **can** combine them_

- Item 1
- Item 2
  - Item 2a
  - Item 2b

1.  Item 1
1.  Item 2
1.  Item 3
1.  Item 3a
1.  Item 3b

http://github.com - automatic!

[GitHub](http://github.com)

As Kanye West said:

> We're living the future so
> the present is our past.

I think you should use an
`<addr>` element here instead.

```javascript
function fancyAlert(arg) {
  if (arg) {
    $.facebox({div: '#foo'});
  }
}
```

- [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> supported
- [x] list syntax required (any unordered or ordered list supported)
- [x] this is a complete item
- [ ] this is an incomplete item

| First Header                | Second Header                |
| --------------------------- | ---------------------------- |
| Content from cell 1         | Content from cell 2          |
| Content in the first column | Content in the second column |

<iframe
  width="640"
  height="390"
  src="http://www.youtube.com/embed/SB-qEYVdvXA"
  frameborder="0"
/>
