Title: FAQ
Date: 2016-01-01 06:00

### Why Viz?

Viewing raw stats and tables only tell you **part of a story**.

![Imgur](http://i.imgur.com/bIryNpL.png)

`Viz` helps tell the rest of the story with **interactive visualizations** that are **continually updated**.

![Imgur](http://i.imgur.com/HBzXqrN.png)

### How Do We Help or Stay Up-To-Date With the Evolution of Viz?

`Viz` is just getting started.  Help spread the word!

[Contributions](https://github.com/donnemartin/viz/blob/master/CONTRIBUTING.md) and [feedback](https://github.com/donnemartin/viz/issues) are welcome.

Feel free to [follow](https://www.github.com/donnemartin), [star](https://github.com/donnemartin/viz/fork), [fork](https://github.com/donnemartin/viz/fork), and check back for updates.

<iframe src="https://ghbtns.com/github-btn.html?user=donnemartin&type=follow&count=true" frameborder="0" scrolling="0" width="145" height="20"></iframe>
<iframe id="gh-star" src="https://ghbtns.com/github-btn.html?user=donnemartin&amp;repo=viz&amp;type=watch&amp;count=false" allowtransparency="true" frameborder="0" scrolling="0" width="50" height="20"></iframe>
<iframe id="gh-fork" src="https://ghbtns.com/github-btn.html?user=donnemartin&amp;repo=viz&amp;type=fork" allowtransparency="true" frameborder="0" scrolling="0" width="53" height="20"></iframe>

<a name="can-i-viz-offline"></a>
### Can I Viz Offline?

Yes, you'll need the **free** [Reader](http://www.tableau.com/products/reader).  Download and run the latest [Viz Workbook](https://github.com/donnemartin/viz/tree/master/viz).  This allows you to interact with a **local copy**--you'll probably want to refresh your workbook as updates are pushed.

Depending on your setup, you'll likely see **improved performance running `Viz` locally.**

### Why Isn't the Online Interactive Viz Loading for Me?

The visualization hosting service might be having issues.  Check the [status](https://trust.tableau.com/status/tableau-public).

You can also run `Viz` offline.

### Can We See Visualizations in JavaScript, Python, R or ...?

Please check out the following [ticket](https://github.com/donnemartin/viz/issues/11).

### What Data Is Tracked?

Although [GitHub Trending](https://github.com/trending) is a **great tool to discover up-and-coming projects**, it only allows you to review up to **one month** of data.  Third-party sites often show **all-time stats** that are **relatively static**, as they are dominated by well-established repos.

`Viz` is meant to supplement existing solutions by **filtering only on the newest, most popular repos** created within a specific timeframe.

***For example, `Viz` 2015 will only track repos created within the year 2015.***

### Can We See Stats for Time Ranges Other Than 2015?

For the initial launch, `Viz` provides stats for 2015.

**Visualizations for 6-, 3-, and 1-month ranges are [under development](https://github.com/donnemartin/viz/issues)**.  The data for each range will be continually updated to keep `Viz` fresh.

### Can We See Stats for 'Older' Repos?

In the future, `Viz` can be extended to track repos regardless of creation date.  Feedback on this [ticket](https://github.com/donnemartin/viz/issues/9) is welcome.

### How Do You Mine Data?

Mining data directly from GitHub, `Viz` is powered by the [GitHub API](https://developer.github.com/v3/) and leverages the following:

* [`github3.py`](https://github.com/sigmavirus24/github3.py) to access the GitHub API through Python.
* [`pandas`](https://github.com/pydata/pandas) and [`numpy`](https://github.com/numpy/numpy) in the following [IPython Notebook](https://github.com/donnemartin/viz/blob/master/githubstats/data_wrangling.ipynb) for data wrangling.
* [Google Maps API](https://developers.google.com/maps/?hl=en) through [`geocoder`](https://github.com/DenisCarriere/geocoder) for location data.
* [Tableau Public](https://public.tableau.com/s/) for visualizations.*

**Interested in visualizations with JavaScript, Python, R, or ...?  Check out the following [ticket](https://github.com/donnemartin/viz/issues/11).*

### Where Do We Find the Data?

* [Data](https://github.com/donnemartin/viz/tree/master/githubstats/data)
* [Data Tables](https://github.com/donnemartin/viz/tree/master/language_stats)
* [Tableau Workbooks](https://github.com/donnemartin/viz/tree/master/viz)

### When Did You Mine the 2015 Data?

The `Viz` 2015 stats were mined on `January 1, 2016, between 00:00 to 01:00 PDT` and include all repos created in the year 2015.  The data is preserved [here](https://github.com/donnemartin/viz/tree/master/language_stats/2015_frozen).

### Why Are My 2015 Manual Search Results Different From Viz 2015?

With [GitHub Search](https://github.com/search), you can manually run queries similar to what you would get from the GitHub API.

To view the most-starred JavaScript repos created in 2015, run the following [query](https://github.com/search?utf8=%E2%9C%93&q=created%3A2015-01-01..2015-12-31+stars%3A%3E%3D100+language%3Ajavascript&type=Repositories&ref=searchresults):

    created:2015-01-01..2015-12-31 stars:>=100 language:javascript

To check stats for a user's or an org's repos that were created in 2015, run:

    created:2015-01-01..2015-12-31 stars:>=100 user:user_name

*Star counts from the searches above will show data up to the time you performed the search.*

### Why Restrict Search Results to `stars:>=100` for Viz 2015?

Only repos with `stars:>=100` are tracked to help filter GitHub's rapidly growing **30+ million** repositories and to keep within the [GitHub API rate limits](https://developer.github.com/v3/rate_limit/).

`Viz` 6-, 3-, and 1-month might loosen this restriction as there should be less repos to analyze.  [Google BigQuery](https://cloud.google.com/bigquery/) along with [GitHub Archive](https://www.githubarchive.org/) could also supplement the GitHub API.

### Why Stars and Forks?

`Viz` provides stats for repos, users, and orgs by stars (and in many cases, forks).  **Stars and forks are *not* perfect metrics**, yet they are **simple and fairly effective measures of interest**.  For a more detailed discussion on measuring repo popularity, check out ["On the Popularity of GitHub Applications:
 A Preliminary Note"](https://github.com/donnemartin/viz/blob/master/assets/gh-stats.pdf) which concludes:

>The number of stars of a system tends to correlate not only with the number of forks, but
also with its effective usage by other client applications, which reinforces the importance
of stars as a real measure of a system’s popularity.

In the future, other stats such as issues, pull requests, followers, etc could be included.

### How Are Stats for Users and Orgs Calculated?

To provide stats for users and orgs, `Viz` groups stars and forks by user or org.  Note the `stars:>=100` restriction still applies.

### What Languages Are Tracked?

`Viz` tracks the most popular languages on GitHub plus the `Unknown` language option.  Repo languages are identified by [github/linguist](https://github.com/github/linguist).

Missing a popular language below?  Feel free to file a [request](https://github.com/donnemartin/viz/issues).

```
languages = [
    'JavaScript',
    'Java',
    'Objective-C',
    'Python',
    'Swift',
    'Go',
    'PHP',
    'C++',
    'C',
    'CSS',
    'HTML',
    'Ruby',
    'C#',
    'Shell',
    'Scala',
    'Clojure',
    'CoffeeScript',
    'Lua',
    'Haskell',
    'VimL',
    'R',
    'Perl',
    'Unknown',
    'Overall',
]
```

### Is Viz Affiliated With GitHub?

No, `Viz` is not affiliated with GitHub.

`Viz` is a community project by the GitHub community, for the GitHub community.

### How Do We Contribute?

Please review the [Contributing Guidelines](https://www.github.com/donnemartin/viz/CONTRIBUTING) for details on how to:

* Submit issues
* Submit pull requests

Check out the [issue tracker](https://github.com/donnemartin/viz/issues).

### How Do We Contact You?

Contact details are on my [GitHub Profile](https://github.com/donnemartin).

You can also file a ticket on the [issue tracker](https://github.com/donnemartin/viz/issues).

### What Is the License for Viz?

    Copyright 2016 Donne Martin

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.