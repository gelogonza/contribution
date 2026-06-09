# Contribution #1: Add loading skeleton for stats cards on Holdings and Positions pages

**Contribution Number:** 1  
**Student:** Angelo Gonzalez  
**Issue:** [Issue #1008](https://github.com/marketcalls/openalgo/issues/1008)  
**Status:** Phase I — In Progress

---

## Why I Chose This Issue

I chose this issue because it has technologies that I use. It is revolved around my interests and I think there's enough documentation to be able to implement a fix for it.

I'm intereted because:
1. it works with Typescript and React
2. I get to learn about UX loading states and how to make designs look better
3. The maintainer comments were descriptive enough to indicate how to approach the problem and how to implement a solution.

---

## Understanding the Issue

### Problem Description

Skeletons aren't made yet for the loading animations of the cards. Current implementation only shows "---".

### Expected Behavior

Fix is to show a skeleton animation while the cards and their details load.

### Current Behavior

Empty screen with "---" as the current behavior for the cards.

### Affected Components

Stats cards for the Holdings and Positions pages.

---

## Reproduction Process

### Environment Setup

Not many issues, really straightforward setup due to the README.md explaining how to set everything up.

### Steps to Reproduce

1. Load the project
2. Navigate to the part that needs fixed
3. Result is proper skeletons implemented using their shadcn component

### Reproduction Evidence

- **Commit showing reproduction:** [feature/skeleton-loader](https://github.com/marketcalls/openalgo/compare/main...gelogonza:openalgo:feature/skeleton-loader)
- **Screenshots/logs:** N/A
- **My findings:** Skeleton components were not being used on these pages

---

## Solution Approach

### Analysis

Components weren't being used for the specific pages that needed to be fixed.

### Proposed Solution

Imported skeleton component, added `isLoading` for the stats cards so the skeletons appear when loading into the page originally. Then render the cards after the skeleton loading animation.

### Implementation Plan

Using UMPIRE framework (adapted):

**Understand:** Skeleton cards not being implemented for the Holdings and Positions pages.

**Match:** Some pages use skeletons; have to reciprocate a similar approach.

**Plan:**
1. Modify Holdings and Positions page files to have the skeleton loader
2. Import `Skeleton` from existing components in all three gaps
3. Make sure the skeleton dimensions match actual text content

**Implement:** [PR diff](https://github.com/marketcalls/openalgo/compare/main...gelogonza:openalgo:feature/skeleton-loader)

**Review:** Follows guidelines for the repository that's being worked on.

**Evaluate:** Running locally on my own machine and making sure the skeletons are fully loading.

---

## Testing Strategy

### Manual Testing

Tested visually with the cards loading as skeletons before the data fully loaded when being on these pages. Making sure that they appear in the manner that they were supposed to appear in.

---

## Implementation Notes

### Week 1 Progress

Skeleton rectangles instead of the current code that is being used for the cards.

### Week 2 Progress

Continue documenting as you work.

### Code Changes

- **Files modified:**
  - `frontend/src/pages/Holdings.tsx`
  - `frontend/src/pages/OrderBook.tsx`
  - `frontend/src/pages/Positions.tsx`
- **Key commits:** [PR changes](https://github.com/marketcalls/openalgo/pull/1485/changes/06d7309e80a4f557adddeff260f6d13548c556cf)
- **Approach decisions:** Most straightforward approach based on the given issue

---

## Pull Request

**PR Link:** [PR #1485](https://github.com/marketcalls/openalgo/pull/1485)

**PR Description:**

**Summary of changes**

- Holdings, Positions, and OrderBook stats cards show skeleton rectangles instead of `---` or `0` while data loads
- Imported `Skeleton` from the existing `@/components/ui/skeleton` component in all three pages
- Skeleton dimensions match actual `text-2xl` CardTitle content (`h-7`, widths vary by content type)

**Testing plan**

- Hard-reload Holdings page with Slow 3G throttle — stats cards pulse grey before data populates
- Hard-reload Positions page — same behavior
- Hard-reload Order Book page — same behavior
- After data loads, skeletons are gone and real values render correctly
- Manual Refresh button does not re-trigger skeleton (`isLoading` stays false on refresh)

**Maintainer Feedback:**
- [Date]: Summary of feedback received
- [Date]: How you addressed it

**Status:** Awaiting review

---

## Learnings & Reflections

### Technical Skills Gained

Pull requests and communicating with maintainers when working on open source contributions. Skeleton loading patterns. Conditional rendering in React, UX loading states.

### Challenges Overcome

Setting up an admin account and getting it to work for local development of this project.

### What I'd Do Differently Next Time

Give a better description of the fix implemented when commenting on the issue, asking for more documentation as well.

---

## Resources Used

- [Issue #1008](https://github.com/marketcalls/openalgo/issues/1008)
