# Contributor Guide

**Image Source** is a responsive React web application built by volunteers from the YouVersion community. If you want to contribute to this project, take a few minutes to read through these Guidelines before submitting your first Pull Request.

## Thank You! 😎
Right up front, let me say, *"THANKS!"* We appreciate that you're willing to use your limited free time to help us engage the world with God's Word. We don't take our mission lightly, and we fully believe we're stronger when the Church works together to accomplish it.

## Getting Started 🤔
- Make sure you have a [Github account](https://github.com/signup/free).
- Make sure you have a [YouVersion account](https://www.bible.com/sign-up).
- Join our Open Digerati Slack Channel:
 - Go to [OpenDigerati.com](https://opendigerati.com/)
 - Click the *Slack* link at the top of the page
 - Enter and then verify your email
 - Once you're in the Open Digerati workspace, look for the `#yv-image-source` channel
 - Once you're in the `#yv-image-source` channel, mention me (`@Michael Martin`) so I can add you to our `YouVersion Volunteers` team in Github.

## Pick Your First Issue 🤩
We're using Github Projects and Issues to manage this project. Everything that needs to be done is organized into bite-sized issues that can usually be completed in a few hours. No contribution is too small, so even if you only have a couple of hours available there's something for you.

- Open the [Image Source Project Board](https://github.com/lifechurch/img-src/projects/1)
- Find an Issue card in the `To do` column that isn't assigned to anyone. The highest priority items are at the top of the list.
- Open the issue and assign it to yourself. If you don't see your name in the list of assignees, make sure you were added to the `YouVersion Volunteers` team in Github.
- Go back to the [Image Source Project Board](https://github.com/lifechurch/img-src/projects/1) and drag your Issue into the `In progress` column.
- There will be many volunteers contributing to this project, so please don't assign as issue to yourself until you're ready to start working. And, if you've assigned an issue to yourself that you cannot work on, un-assign the issue and drag the card back to the `To do` column for someone else to pick up.

## Git
- Clone this repo
- Create a branch with the following naming convention: `{your-initials}/issue-{issue-id}`. For example, I might create a branch called `mm/issue-1`.
- Write your code. Do your best to make each commit fully functional. In other words, don't commit code to your branch that you know is not working.
- Don't include closing keywords (`Closes #2` or `Fixes #1`) on the individual commits.
- When your feature is complete and ready for review submit a Pull Request. In the body of the request, include a line stating which issue the PR addresses. Like this, `Fixes #1`. This is vital to our project workflow. Otherwise, it's cumbersome to determine which issues have been resolved.

## Writing the Code 🤓
Now that you have your first issue, it's time to write some code. But, before you dive in let's talk about a few things. I promise we're not mean or rude. We want to lower the bar for contribution as low as possible. But, we do have a few expectations for this project.

### ESLint - Don't break the rules
We use [ESLint](https://eslint.org/) to perform a static analysis of our code and identify problematic patterns and style issues that don't line up with the way we do things. Most IDEs and text editors support `ESlint`. We recommend [Atom](https://atom.io/), [Sublime](https://www.sublimetext.com/) or even [VSCode](https://code.visualstudio.com/). They each have plugins that automatically validate your code against our linting rules every time you save a file. Plus, we use [Code Climate](https://codeclimate.com/) to check all of your code when you submit a Pull Request.

If your code violates any of our linter rules, we probably won't merge your Pull Request until you fix them. Don't worry! 😰 We'll work with you to fix the issues so your hard work doesn't go to waste.

### CSS - Tachyons Only
For this project, we're using the [Tachyons](http://tachyons.io/docs/) CSS framework. Using the framework keeps our CSS [D.R.Y](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself). Tachyons defines numerous classes for margin, padding, typography, grid layouts and more. Be sure to checkout [tachyons.io](http://tachyons.io/docs/) for documentation on what's available.

Since Tachyons is so comprehensive, we rarely need to create or modify CSS classes. That also means that we rarely need new CSS, LESS or SASS files. So, as you're building your components do your best to use Tachyons classes exclusively. If you define new CSS classes or add new CSS files, we probably won't merge your Pull Request without proper justification. But, admittedly, there will likely be a FEW exceptions to this -- but only go outside of Tachyons as a last resort.

### PropTypes
Be sure to define [PropTypes](https://github.com/facebook/prop-types) for every property on the React components you build. This is part of the linter rules, but it's worth mentioning again. These PropTypes define the component contract that other developers will need when trying to use your component

### Component Naming / Folder Structure
For naming your components, here's a few general guidelines:
- Don't include the word `component` in the file name or the class name
- Name your files using hyphens (i.e. `./components/round-button.js`) instead of `camelCase`
- Name your classes using camelCase (i.e. `class RoundButton extends Component`)
- Small UI components used in multiple places should be located in `/src/components/{component-name}/index.js`
- Page-level components that are tied to routes should be located in `/src/containers/{container-name}/index.js`
- UI components that are only used once, but don't represent a full page should be stored under the container in which they're rendered: `/src/containers/{container-name}/components/{component-name}/index.js`