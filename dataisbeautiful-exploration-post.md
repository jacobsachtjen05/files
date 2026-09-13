---

---

# Data Is Beautiful Exploration

For this assignment I browsed r/dataisbeautiful (sorting by a mix of Hot and Top rather than sticking to the default) and looked for posts that felt like they'd resonate with a Digital Humanities crowd, leaning toward text, language, culture, and history over pure finance or sports charts. Here are the five I settled on, and what I found digging into each one.

## 1. [A Life in Books](https://www.reddit.com/r/dataisbeautiful/comments/1jobwwu/a_life_in_books/)

What makes this one interesting to me is the sheer dedication it takes to track every single book you read, and want to read, for over two decades straight. It's honestly admirable. Most people can't keep up a habit like that for a month, let alone half their life.

None of this data came from an outside source. It's entirely self-collected: the poster has manually logged every book they own or want to read for over 20 years, starting around the beginning of high school. That makes the original data individual-book-level records, things like title, format, genre, page and word count, audiobook duration, rating, publication date, and date read, almost certainly kept in a personal spreadsheet with one row per book.

The presentation is what turns raw tracking into something worth reading. The "Books Read per Month" chart overlays life events (started dating, quit job, got married, baby due) directly on the reading timeline, turning a bar chart into something closer to a data memoir. The scatter plots, like word count versus duration with an R² of 0.991, also give a satisfying statistical payoff to something intuitive, made more convincing because it's 20+ years of one person's own data.

If I tried this myself, I'd start with something as simple as a Google Sheet, one row per book with title, genre, page count, and date finished, since that's basically free and matches what this poster likely used. The real trick is just starting today; you can't backfill 20 years of data, so the earlier you start logging, the more interesting the eventual chart gets.

## 2. [Roman Emperors 27 BCE – 395 CE](https://www.reddit.com/r/dataisbeautiful/comments/1iw1qce/oc_visualizing_the_lifetimes_and_reigns_of_a/)

What stood out most to me was how common assassination was as a cause of death. Rather than being the exception, it was practically the default way a Roman emperor's reign ended. That says a lot about how unstable and violent succession in the empire actually was, way more than I'd have guessed.

The data itself comes from a public GitHub dataset (zonination/emperors) compiling reign dates, birth and death dates, and manner of death, structured as tabular data with one row per emperor. The poster was upfront that they hadn't yet cross-checked it against scholarly sources.

Mapping each emperor's life as a full birth-to-death circle with the reign highlighted as a golden arc is a much more visceral metaphor than a plain timeline. You immediately see how much of a life was spent as emperor versus everything else. The manner-of-death icons (dagger, axe, crossed swords, broken heart) turn a grim dataset into something scannable at a glance, and the poster linked their full Jupyter notebook and posted two transparent updates fixing an error and incorporating feedback.

I'd probably start simpler than Vega, using a basic Python script with matplotlib to plot birth-to-death arcs, and pull the emperor list straight from Wikipedia rather than trusting an unverified GitHub dataset for something as sensitive as "manner of death," since that's exactly the kind of detail that needs a real source check.

## 3. [Proportion of Unicode 17.0 Characters Originating in China, Japan, and Korea](https://www.reddit.com/r/dataisbeautiful/comments/1ky9bs3/proportion_of_unicode_characters_originating_in/)

This connects to something I already found fascinating: how Chinese internet users have used the sheer richness of the character set to get around government censorship, picking characters that sound like banned terms instead of writing them directly. Seeing the actual scale of the character set behind that workaround, over 100,000 Han characters alone, made that phenomenon click in a new way.

The source here is about as primary as data gets: the Unicode Consortium's own published standard, specifically the Unicode 17.0 draft files (UnicodeData.txt, Scripts.txt, Blocks.txt, emoji-data.txt), the literal spec that defines how characters get encoded on every computer. It comes as plain-text data files, one line per character or character range, listing which script or block it belongs to. That's structured, but not spreadsheet-ready without parsing.

The giant 字, the character for "character," in the middle of the donut signals the topic before you read a word. Putting the obscure scripts (Yi, Tangut, Phags-pa, Nüshu) in a written glossary below the chart, rather than just labeling slices, is what makes the post educational rather than just decorative. A paragraph explaining Nüshu was a script secretly used by Yao women in Hunan does more work than a "0.3%" label ever could.

I'd use Python to parse the raw Unicode data files the same way the original poster did, then chart it in something quick like Google Sheets or matplotlib. It'd also be interesting to run the same breakdown on an older Unicode version and compare how the proportions have shifted as new scripts get added.

## 4. [Top 5 Countries, Eurovision Song Contest](https://www.reddit.com/r/dataisbeautiful/comments/1ksnbph/oc_how_public_and_jury_votes_affect_the/)

The tension between the jury and public vote is the most interesting part to me: it's basically built-in drama every year, where the "experts" and the general audience can wildly disagree on who actually deserved to win.

The underlying data comes from eurovisionworld.com, which tracks detailed jury versus public vote breakdowns, compiled by the poster into their own public dataset. It's per-country, per-year voting results, jury rank and public rank, likely scraped or manually compiled into a clean CSV.

The gray bar connecting jury and public vote dots tells the whole story in one visual element: a long bar means the juries and public disagreed wildly. Bolding the winning country's marker each year draws attention to whether the winner actually had consensus. Worth noting, the poster made an aggregation error in the 2017 row, a Redditor caught it in the comments, and the poster republished a corrected version transparently, a nice example of public data getting peer-reviewed in the wild.

Given the aggregation mistake the original poster made, I'd double check the raw per-country vote totals against the official Eurovision results page before charting anything, then stick with a similar dumbbell-style chart since the gap between jury and public rank is really the whole point.

## 5. [Mean Confidence in 13 National Institutions, by Partisanship, 1974–2024](https://www.reddit.com/r/dataisbeautiful/comments/1ky3tfs/oc_american_confindece_in_national_institutions/)

I already had a rough sense of most of these trends going in, but seeing the actual numbers laid out made it hit differently. Some of the declines, especially in things like Congress and the press, were worse than I'd assumed just from following the news.

The data comes from the General Social Survey (GSS), a long-running academic survey that's asked Americans the same core confidence questions since the 1970s specifically to track opinion change over time, drawn here from the GSS Cumulative File covering 1972 to 2024. It started as individual-level survey responses, each respondent's 1 to 3 confidence rating per institution plus party affiliation, which the poster then aggregated into annual party-level averages.

Keeping every panel on the same y-axis scale lets you compare confidence levels across institutions, not just trends within one. The shaded ribbon between the red and blue lines turns "how far apart the parties are" into a single shape you can read at a glance, and its color flips visibly for institutions like the Supreme Court or Military. Printing the exact survey question at the top is a transparency choice that lets you judge the framing for yourself.

I'd pull the raw data through the GSS's own online data explorer rather than downloading the full cumulative file, then use R with ggplot2's facet_wrap to recreate the small-multiples layout. I'd want to be careful the smoothing doesn't flatten out real single-year spikes, like a scandal-driven confidence drop.

## Wrap-up

Looking back across all five, what struck me is how differently "interesting" showed up in each one. Sometimes it was raw human dedication (the reading tracker), sometimes a single surprising fact (assassination as the default emperor death), sometimes a connection to something I already cared about (Unicode and censorship evasion), sometimes built-in drama (Eurovision's jury vs. public split), and sometimes just seeing a hunch confirmed with hard numbers (the institutional confidence survey). That range made me think about how differently the same five reflection questions can land depending on whether the data is deeply personal, historical, technical, competitive, or civic.

---
*Sources: linked inline above. Additional data sources referenced by original posters: [zonination/emperors](https://github.com/zonination/emperors), [Unicode 17.0 draft](https://www.unicode.org/Public/draft/ucd/), [eurovision_song_contest_data_set](https://github.com/thomascamminady/eurovision_song_contest_data_set), [General Social Survey](https://gss.norc.org/us/en/gss/get-the-data.html).*
