# Existing design material review and notes

### Introduction

This is an unrefined collection of notes taken by me (@blahah) as I review the documents in this repo that were developed previously.

It will be iterated upon and may have repeated ideas and notes. Parts that failed to account for existing information will be removed/refined iteratively.

I will be leading development of the system, and continuing from the design process followed so far. I was not part of the initial design session, so this is part of my process for building effectively and efficiently on what was produced in that session.

The purpose of these notes is:
- to allow me to understand the process that was used
- to understand the decisions made and outputs that were created
- to distil out anything relevant to how we continue the process, e.g.:
  - how we can collaborate effectively as a remote, distributed team going forward
  - any aspects of the initial process that might need to be revisited
  - how the design process might be continued so that it connects to the development process

There may be some overlap between this document and the notes in `design_thinking` - this is to help me keep key things in context during review.

### acronyms used below

- US: User Story
- F: Feature
- (Q): question raised during review
- (C): concept - suggests an abstraction of a concept, visual interface component, or mental model

### Basic summary of the `design_thinking` methodology

- user empathy centered process led by Giuliano from eLife
- participants included Daniela (project leader), Giuliano and Nick from eLife, and other stakeholders
- key user types identified
  - (C: user entity)
  - (C: roles)
  - (C: permissions)
- user stories for each user type written, collated and ranked for priority
- those essential for MVP selected and distilled into features
  - (C: modularity/future development facilitation)
- some features essential for MVP converted to UI mockups of specific views by Nick from eLife


[PREreview-2.0-design/users_analysis.md at master · PREreview/PREreview-2.0-design · GitHub](https://github.com/PREreview/PREreview-2.0-design/blob/master/design_thinking/users_analysis.md)

## Notes on individual mockups

### Home screen (logged out) showing feed

[PREreview-2.0-design/pre-print-home-feed@2x.png at master · PREreview/PREreview-2.0-design · GitHub](https://github.com/PREreview/PREreview-2.0-design/blob/master/mockups/pre-print-home-feed%402x.png)

- Large header centering organisational identity
- Call to action for key task: 'Submit a preprint'
  - (C: preprint entity)
- Top menu with logo (left) and signin/register (right)
  - (C: top bar)
  - (C: top bar logo)
  - (C: identity)
  - (Q: has the concept of identity been defined and any constraints on its role in the system defined?)
  - (Q: do users have to map to identities?)
  - (C: identity creation / ingress)
  - (C: user relation one-to-one -> identity)
  - (C: identity preservation across contexts)
- Feed of preprints that have been reviewed recently
  - (C: feed)
  - (C: feed item preprint)
  - options for sorting the feed
    - (C: feed content sorting)
    - (Q: what are the options beyond the visible 'date')
  - options for filtering the feed by tags
    - (C: feed item metadata)
    - (C: feed content filtering on metadata)
  - (C: feed display control)
  - (C: multiple / intersecting effects of controls)
- each feed item
  - draws attention to the title and tag/field
    - (C: preprint entity metadata)
    - (Q: are these tags or categories or both?)
    - (Q: are the possibilities here predefined or user defined/suggested)
      - (Q: if user defined/suggested are they constrained by an ontology/dictionary?)
  - includes submission date and submitter
    - (Q: submitter of preprint to the PREreview platform or author(s) of preprint?)
    - (C: identity within/outside the PREreview context)
    - (Q: can the user decide whether their identity is exposed in any given context?)
      - (C: user identity data control permissions)
      - (C: can a user decide whether their identity is hidden each context individually? e.g. be hidden for this review/comment)
      - (C: contextualised permissions)
  - number of reviews
    - (Q: is this a link to the list of reviews?)
    - (C: review)
    - (C: entity relation one to many, preprint -> review)
  - call to action to add a review
    - (C: preprint entity import/creation)

### Home screen (logged out) showing submit preprint modal form

[PREreview-2.0-design/pre-print-home-submit-pre@2x.png at master · PREreview/PREreview-2.0-design · GitHub](https://github.com/PREreview/PREreview-2.0-design/blob/master/mockups/pre-print-home-submit-pre%402x.png)

- modal form displayed over initial home screen
- no login required at this point implied
  - (Q: UX flow for login before submission is made?)
  - (C: identity and contextual permissions)
  - (C: unknown identity / 'not logged in')
- form
  - preprint URL
    - (Q: or DOI?)
    - (C: preprint entity linked data / metadata)
    - (Q: has research about preprint platforms, their metadata standards, APIs been performed/collected?)
    - (Q: is there already a central organisation representing preprint platforms/organisations where we can source information?)
  - Manuscript title
    - (Q: do we need to ask this?)
    - (C: inferring / importing metadata)
    - (Q: what US/F is this derived from?)
  - reason for submitting dropdown
    - (Q: what are the options?)
    - (Q: what US/F is this derived from?)
    - (Q: does the first review import/create the preprint entity within the system?)
      - (Q: if so, is a reason associated with every review or only the first one?)
    - (C: reason metadata associated with preprint/review)
  - Cancel button
    - (C: workflow exit)
  - Submit button (attention drawn)
    - (C: preprint/review entity data ingress)
    - (C: local vs PREreview system storage)
    - (C: transition of locally stored data to PREreview system)

### Review history for a particular user

- top bar consistent with home page
  - (C: top bar)
- icon for user
  - (C: user entity metadata icon)
  - (Q: where does this come from?)
  - (Q: can the user choose/change it inside PREreview system?)
  - (Q: is there a default?)
  - suggests that user has identity and is logged in
  - suggests that icon is clickable with further UX flow
    - (Q: is that further UX flow designed?)
    - (Q: assuming identity has an associated view, is it different when identity views itself vs one/unknown identity viewing that of another)
- bell icon
  - suggests a notification feature and icon that has further UX flow
  - (C: notification)
  - (Q: what US/F does this map to?)
  - (Q: is that further UX flow designed?)
- feed of reviews in reverse date order
  - consistent with home page feed in style
    - except there's no filtering or ordering UI
    - (C: contextualisation of feed filtering / ordering)
  - individual feed items appear identical to home page
    - (C: default preprint->review feed item)

### Review open interface

[PREreview-2.0-design/review-open@2x.png at master · PREreview/PREreview-2.0-design · GitHub](https://github.com/PREreview/PREreview-2.0-design/blob/master/mockups/review-open%402x.png)

- consistent top bar with review history
  - (C: contextualisation of top bar)
- preprint/review viewing pane
  - (C: split pane view)
  - preprint to left
    - (C: preprint display, split pane context)
  - reviews to right
    - (C: review feed display, split pane context)
    - (C: contextualised feed)
  - call to action to review preprint styled consistently with other calls to action
    - (C: call to action)

### Review Stream interface

[PREreview-2.0-design/review-stream@2x.png at master · PREreview/PREreview-2.0-design · GitHub](https://github.com/PREreview/PREreview-2.0-design/blob/master/mockups/review-stream%402x.png)

- appears generally identical to Open interface
  - except it shows the UI at the end of a review, with the review text (example in Open interface was too long for this to display in the mockup)
  - individual review in stream
    - reviewer identity
    - review date
      - (C: review metadata date)
      - (Q: can reviews be edited?)
        - (Q: is edit history recorded?)
        - (Q: is date displayed creation data, latest edit, or both?)
    - review text truncated with ellipsis
      - (C: review feed item contextual display)
      - (C: review text)
      - (C: review text display control)
    - thumbs up icon with (N thanks) to indicate support for review
      - (C: review endorsement)
      - (Q: is thanking linked to identity?)
        - (Q: can unknown/'logged out' users express thanks?)
        - (C: endorsement relation to identity of endorser)
    - number of comments on review and implied link to show comments
      - (Q: UX flow for this designed?)
      - (Q: comments displayed inline or taken to different view?)
    - 'see more' which implies expanding truncated review text

### Review open comments

[PREreview-2.0-design/review-open-comments@2x.png at master · PREreview/PREreview-2.0-design · GitHub](https://github.com/PREreview/PREreview-2.0-design/blob/master/mockups/review-open-comments%402x.png)

- identical to review open/stream in general
  - except comments are displayed
    - (C: comment)
    - (C: review relation to comments one -> many)
    - (C: feed of comments)
    - (C: comment editor interface contextualised to review feed item)
    - (Q: can comments be edited/saved unpublished and revisited later for editing/publishing?)
    - (Q: can comments be deleted by the user?)
    - (Q: can comments be deleted by site staff?)
    - (C: interface contextualised by user role)
    - inline in right review pane
    - underneath review in context, deliniated
      - (C: contextualised styling of comments)
    - comments consistent with format of review component in open view
      - except deliniated to suggest context encapsulation
      - except no thanks
        (Q: can comments be endorsed?)
      - except no suggestion of expansion/contraction
        (Q: can comments be )
      - except no list of number of comments
      - comments can be commented on
        - (C: relation bidirectional comment <-> comment)
        - (C: comment-comment relation metadata: parent)
        - (Q: can comments have more than one direct reply?)
          - (C: comment relation parent<->child one to many)
        - (C: threading)
        - (C: comment depth context)
    - (Q: are comments conceptually identical to reviews, except relating to either another comment or review?)

### Review write

[PREreview-2.0-design/review-write@2x.png at master · PREreview/PREreview-2.0-design · GitHub](https://github.com/PREreview/PREreview-2.0-design/blob/master/mockups/review-write%402x.png)

- same split view as review open/stream
- right pane is an editing environment instead of a display of reviews
  - (C: review writing/editing environment)
  - (Q: can reviews be saved in an arbitrary state and revisited later for editing?)
  - (Q: can reviews be published and subsequently edited?)
  - (C: review metadata published)
  - (Q: can a published review be deleted by the user?)
  - (Q: can a published review be deleted by site staff?)
  - (Q: can a published review by unpublished without deleting, i.e. to allow more editing?)
  - (Q: are these things affected by whether the review has comments?)
- (Q: are comments expected to have the same editing environment?)
- (Q: fundamental question of the value of reviews vs discussion in context of review)
