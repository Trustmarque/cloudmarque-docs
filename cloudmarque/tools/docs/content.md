---
title: Docs Content Standards
summary: If you'd like to contribute to the documentation please read through these standards to understand our quality expectations.
---
This guide is intended to help both content contributors and Pull Request reviewers to form a shared understanding of content quality controls. While recognising that it's not possible to codify every content rule and that a measure of quality evaluation is subjective, the aim of this page is to set out the expectations and considerations when creating and editing Cloudmarque content.

## Basics
 * Run a spelling and grammar check on your contribution.
 * Content is proudly written in British English (EN-GB):
    - Colour, not color
    - -zation words are -sation (e.g. specialisation, realise, etc)
    - Licence is a noun, licensing is a verb
 * Refer to Cloudmarque by name, no need to add "the Cloudmarque _Standard_" or "the Cloudmarque _Framework_". It's just "Cloudmarque".
 * Refer to readers' group contexts as "organisations", not "company" or "customer".
 * Feel free to write in a conversational second-person ("you") when contextualising solutions for the reader: we find third-person too stilted and boring.

## Form
 * Avoid long unbroken paragraphs which make it hard for users to scan for relevant content.
 * Aim for each paragraph to relate to a single subject.
 * Use a mix of formatting options to break up content: paragraphs, bullet and numbered lists, headings.
 * We run a link checker on pages as part of the build process:
    - The checker won't flag _valid links to the wrong content_: manual checks are essential!
    - External links aren't checked automatically.
 * Don't include scripts or external content (IFRAMES) in pages.
 * A picture paints a thousand words: use them rather than a thousand words.

## Images
 * Create diagrams as SVGs so that they scale nicely. If you're looking for a free editor, we use and recommend [Inkscape](https://inkscape.org/).
 * Use SVG iconography from the relevant cloud platform to create diagrams ([Azure](https://www.microsoft.com/en-gb/download/details.aspx?id=41937), [AWS](https://aws.amazon.com/architecture/icons/)).
 * Label components and arrows directly and/or use a key to explain what components are.
 * Ensure any `alt` tags for images have proper descriptions for accessibility tools to use.
 * Ensure that the image makes sense in context: text paragraphs before and/or after the image should introduce or summarise what is being shown.
 * Where possible please add comparable diagrams for different cloud platforms (AWS/Azure).

We're aware that some imagery and complex content (Liquid includes) is not yet documented, or not included in the _Cloudmarque Docs_ repository. We're addressing these over time as an ongoing background task. Don't worry about where these reside for Pull Requests, we'll confirm target locations as part of the review process.