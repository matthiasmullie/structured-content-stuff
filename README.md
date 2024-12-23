A couple ideas of likely-feasible improvements that would aid image discovery.

Pictures have been added in order to better convey the idea; they'd obviously need someone with actual expertise to fully bake them!

- [In-article suggestions](#In-article-suggestions)
- [Improved media categorization](#Improved-media-categorization)
- [Statements filter in MediaSearch](#Statements-filter-in-MediaSearch)
- [Similar media](#Similar-media)
- [Improve MediaSearch algorithm](#Improve-MediaSearch-algorithm)


# In-article suggestions

We already have a large catalog of article/section image suggestions. Most of them, however, never reach a user.

The current methods either have an extremely limited audience & are cumbersome (notifications), or require dedicated effort by users who may lack insight/interest in the article (structured tasks)

## Proposal

If we could just add something to the article, it is likely to be seen by a lot more (relevant) people, and easy to immediately act on.

Benefits:
- Missing-but-available images are easily discoverable
- Feedback (rejecting would allow discarding the suggestion)

![Proposal: step 1](/img/suggestions-1.png)
![Proposal: step 2](/img/suggestions-2.png)
![Proposal: step 3](/img/suggestions-3.png)


# Improved media categorization

## Current

Below is how uploaders are currently expected to categorize their media files on Commons.
Even though Commons expects media to be categorized as detailed as possible, the autocomplete does not currently facilitate that: unless you already know exactly what that detailed category is, you'll likely never find it and end up assigning it into an overly broad parent category.

![Current](/img/categories-now.png)

## Proposal

Allow drilling down into categories (that have subcategories).

Benefits:
- Better categorized media (and categories are still a dominating force on Commons, with lots of tools using them), which enables:
  - Better moderation
    - Media are in the right place, with the right people looking at them
    - Less work fixing improperly categorized media
  - Better discoverability
    - Browsing the category tree is more likely to enable you to find the right image
    - Categories also feed into MediaSearch, so (slightly) improved results
    - More detailed categories are easier to convert to structured data (e.g. through AC/DC, Depictor, ...), which again yield discovery/search benefits

![Proposal: step 1](/img/categories-1.png)
![Proposal: step 2](/img/categories-2.png)
![Proposal: step 3](/img/categories-3.png)


# Statements filter in MediaSearch

## Current

The MediaSearch interface currently offers little to help you find highly-specific media. Take a look at below search for finding a car in the desert:

![Current](/img/filter-now.png)

## Proposal

In addition to the existing filters (e.g. license, type, size, ...), we could add another that lest the user filter based on custom statements: e.g. "depicts = desert" or "instance of = painting".

Benefits:
- Better discoverability; much more specific searches are possible

![Proposal: step 1](/img/filter-1.png)
![Proposal: step 2](/img/filter-2.png)
![Proposal: step 3](/img/filter-3.png)
![Proposal: step 4](/img/filter-4.png)
![Proposal: step 5](/img/filter-5.png)
![Proposal: step 6](/img/filter-6.png)


# Similar media

Unlike Wikipedia, it's hard to rabbithole on Commons. Other than using the category tree (which is limited in other ways; e.g. subject intersections), finding similar media is neigh impossible.

It could easily be accomplished with statements, but "haswbstatement:" search queries are impractical, and we're certainly not actively exposing such potentially-interesting-because-similar media to users.

Benefits:
- Better discoverability of likely-relevant media you may not otherwise be exposed to

## Per statement

Below is a script I've been running for years now; it simply adds an icon next to each statement, which then leads to a search for images matching that same statement.

![Proposal: step 1](/img/rabbithole-1.png)
![Proposal: step 2](/img/rabbithole-2.png)

## Per file

We could certainly do something similar on a per-file basis, showing other media that match (some) statements of another file.

![Proposal](/img/similar.png)


# Improve MediaSearch algorithm

MediaSearch was a massive leap, but the current algorithm is based on findings from when structured data was still nascent.
Since then, a lot more structured data has been added (e.g. captions and statements could now be provided on upload; bots/tools have filled a lot of gaps, ...) and conventions have changed (e.g. "main subject" has been found to be used inconsistently), and new developments have been done (e.g. weighted_tags data).
Furthermore, the data the initial algorithm was based on was rather English-centric.

Re-examining the relevance of all already-available data and adjusting the weights based on those finding would most likely improve the media search results.
