---
layout: post
title: Detecting widows in React
author: Jeff Chen
tags: resume,json,cv,react
---

I love the [JSON Resume project](https://jsonresume.org/) - splitting résumé design from data is a great idea. But I've noticed a couple problems over time:

- Existing generators only output HTML - so there's no way to know if your résumé is overflowing onto a new line until you convert it to a PDF.
- My list of accomplishments keeps growing but paper sizes sadly stay the same. [Since](https://www.careercup.com/resume) [common](https://www.quora.com/What-should-be-the-length-of-an-8-years-experienced-software-developers-resume-What-are-suggestions-from-recruiters) [wisdom](https://www.quora.com/What-is-the-preferred-length-of-a-CV-resume-for-3-years-of-experienced-developer) is to keep résumés to a single page, I've had to trim some of the less important or older items from my résumé.
- Sometimes I like to tailor my résumé for individual companies - selecting line items and sections to promote.
- I spend way too much time wordsmithing to avoid widows and orphans in my line items.

I [built my own résumé generator](https://www.github.com/jchen1/resume) to solve some of these problems:

- It uses headless Chrome to automatically generate PDFs from the output HTML.
- You can hide or show line items and sections so your JSON can be a source of truth for many generated résumés.
- It will automatically warn you when a line item overflows into a new line and when your résumé no longer fits on a single sheet of paper.

## Generating PDFs from HTML

## JSON as the source of truth

##
