---
layout: post
date: 2015-11-16
title:  Is there a Campaign Against Chelsea?
description: "A statistical analysis of refereeing fairness in football. Does Mourinho have a point: are some teams mistreated by refs?"
og_image: /assets/is-there-a-campaign-against-chelsea/fig-1.png
tags: chelsea, mk dons, sunderland, fouls, bookings, fairness
---

Football managers and fans often cite shoddy refereeing decisions as the reason for their team’s poor results—none more so than Jose Mourinho. Mourinho sparked off the Campaign Against Chelsea<sup><a href="#footnote-1" id="footnote-1-link">[1]</a></sup> debate in the 2014/15 season, and has continued with that theme more recently, having been charged with misconduct over comments he made after his team’s loss at Southampton<sup><a href="#footnote-2" id="footnote-2-link">[2]</a></sup>. But does he have a point? Are some teams mistreated by referees more than others? Are referees influenced by comments published or broadcast in the media?

[Skip to the summary](#summary)

## Fouls & Bookings

To answer these questions, we’ll analyse the stats by comparing **fouls committed** to **bookings received**.

Refereeing complaints might be about any number of decisions: red cards, penalties, offsides, disallowed goals etc. Analysing every controversial decision for every team wouldn’t be practical, but by comparing fouls to bookings, we can get a _sense_ of how each club is treated.

We’d expect the relationship between these two stats to be linear: the more fouls a team commits, the more bookings they should receive, and therefore outliers will highlight teams who are treated more or less favourably.

To directly compare fouls and bookings, we’ll use **booking points** to create a single value representing both red and yellow cards. Booking points are calculated as follows: 10 for a yellow; 25 for a red.

## Analysis

The following graphs plot the average number of fouls committed against the average booking points received (per match), with each team represented as a dot. A team which lies above the line of best fit receives more bookings than the norm for the number of fouls they commit). Likewise, a team positioned below the trend line, receives fewer bookings than the norm.

However, it’d be wrong to conclude that any team lying above the line is mistreated, or that any team below the line is favoured—we need to identify the outliers. We’ll do this with _studentised residuals_. A studentised residual (SR) is a measure of the distance of a point from the trend. In general, a SR with an absolute value greater than 2 or 3 is an outlier<sup><a href="#footnote-3" id="footnote-3-link">[3]</a></sup>. The SR calculation takes into consideration the strength of the correlation, so the weaker the trend, the further out a point has to be to be considered an outlier. SRs are shown in brackets.

<figure class="breakout">
  <h3>
    <span class="figure-number">Figure 1.</span> Avg. Fouls Committed vs. Avg. Booking Points <span class="subheading">covering matches in the 2014/15 and 2015/16 seasons so far</span>
  </h3>
  <img src="/assets/is-there-a-campaign-against-chelsea/fig-1.png" data-uri="/fouls/vs_bookings?division=&start_season=22&end_season=23&highlight_teams[]=73&highlight_teams[]=79&highlight_teams[]=22&highlight_teams[]=89&highlight_teams[]=80&highlight_teams[]=94&highlight_teams[]=66&min_match_count=1">
</figure>

### Have Chelsea been unfairly treated since last season?

First, we’ll look at the stats since last season (roughly the period in which Mourinho has been complaining As you can see from Figure 1, the relationship is  weak—likely due to the low number of matches each team has played. Nevertheless the graph shows that Chelsea, with an SR value of 2.4, are an outlier suggesting that they have indeed been unfairly treated. Mourinho may have a point.

However if there is a Campaign Against Chelsea, then there’s a strong case for a **Campaign Against Sunderland**, too. With an SR of 3.2, Sunderland appear to have had the worst treatment during this period. They commit the same number of fouls as Leicester (11.6/match), yet they average 26.5 booking points per match—10 more than Leicester, and the equivalent of one yellow card more per match. Perhaps it’s no coincidence that Lee Cattermole received the joint-highest number of yellow cards in a Premier League season last year (14)<sup><a href="#footnote-4" id="footnote-4-link">[4]</a></sup>.

Finally, as a Brighton fan, I must to point out that **Crystal Palace** have the highest average fouls per match—slightly more than their South London neighbours **Millwall**.

### Are some teams treated favourably or unfavourably?

To attempt to draw more meaningful conclusions, we’ll examine the same stats since the 2000/01 season. The weak correlation in Figure 1 showed us that refereeing decisions don’t even out over the course of a season (with regards to bookings at least), so we’ll exclude teams who played fewer than 190 matches (~4-5 seasons) during this period. This will hopefully prevent teams who only played few games from skewing the results.

<figure class="breakout">
  <h3>
    <span class="figure-number">Figure 2.</span> Avg. Fouls Committed vs. Avg. Booking Points <span class="subheading">for teams who have played more than 190 league matches since 2000/01</span>
  </h3>
  <img src="/assets/is-there-a-campaign-against-chelsea/fig-2.png" data-uri="/fouls/vs_bookings?division=&start_season=8&end_season=23&highlight_teams[]=1&highlight_teams[]=6&highlight_teams[]=73&highlight_teams[]=15&highlight_teams[]=101&highlight_teams[]=18&highlight_teams[]=89&highlight_teams[]=40&highlight_teams[]=76&min_match_count=190">
</figure>

As you can see in Figure 2, the correlation is much stronger. Chelsea are still up there, but not an outlier. From the current league teams, **Crewe** commit the fewest number of fouls on average (8.4/match), whereas **Millwall** are guilty of the most with 13.5/match (Boston are in the National League North; Chester City existed until 2010).

By far the most outstanding result is **Milton Keynes Dons**, who seem to receive way more bookings than they perhaps should do. On average, they commit the same number of fouls as Arsenal, but get punished as if they are Millwall. This may have something to do with their controversial existence<sup><a href="#footnote-5" id="footnote-5-link">[5]</a></sup>, making them disliked by crowds of football fans (and referees, too?).

Other notable teams include Accrington Stanley ([who are they?](https://www.youtube.com/watch?v=pieK7b4KLL4)), Southampton and Cheltenham (who are both somewhat favoured).

### Are referees influenced by the media?

Mourinho blamed “media, commentators, [and] other managers” for putting pressure on referees and therefore influencing their decisions. If this is the case, we’d expect referees’ decisions to be inconsistent while the press alter their stance on different teams, players, or managers. And given that the Premier League gets the lion’s share of media coverage, we’d expect this effect to be most pronounced in this top tier.

A nice feature of these scatter plots is that the strength of the trend represents the consistency of refereeing for the given data set. By isolating matches played in each division, we can see how consistent the refereeing is at each level.

The r<sup>2</sup> values denote the strength of the trend, where 0 represents no correlation and 1 is perfect correlation. Tap on a graph to see an annotated version.

<h3>
  <span class="figure-number">Figure 3.</span> Comparison of Fouls to Booking Points across Leagues
  <span class="subheading">for teams who have played more than 190 league matches since 2000/01</span>
</h3>

<div class="figure-grid breakout">
  <figure>
    <figcaption><span class="figure-id">Figure 3a.</span> Premier League (r<sup>2</sup>: 0.20)</figcaption>
    <a href="/assets/is-there-a-campaign-against-chelsea/fig-3a-e0-annotated.png"><img src="/assets/is-there-a-campaign-against-chelsea/fig-3a-e0.png" data-uri="/fouls/vs_bookings?division=1&start_season=8&end_season=23&min_match_count=190"></a>
  </figure>

  <figure>
    <figcaption><span class="figure-id">Figure 3b.</span> Championship (r<sup>2</sup>: 0.45)</figcaption>
    <a href="/assets/is-there-a-campaign-against-chelsea/fig-3b-e1-annotated.png"><img src="/assets/is-there-a-campaign-against-chelsea/fig-3b-e1.png" data-uri="/fouls/vs_bookings?division=2&start_season=8&end_season=23&min_match_count=190"></a>
  </figure>

  <figure>
    <figcaption><span class="figure-id">Figure 3c.</span> League One (r<sup>2</sup>: 0.62)</figcaption>
    <a href="/assets/is-there-a-campaign-against-chelsea/fig-3c-e2-annotated.png"><img src="/assets/is-there-a-campaign-against-chelsea/fig-3c-e2.png" data-uri="/fouls/vs_bookings?division=3&start_season=8&end_season=23&min_match_count=190"></a>
  </figure>

  <figure>
    <figcaption><span class="figure-id">Figure 3d.</span> League Two (r<sup>2</sup>: 0.55)</figcaption>
    <a href="/assets/is-there-a-campaign-against-chelsea/fig-3d-e3-annotated.png"><img src="/assets/is-there-a-campaign-against-chelsea/fig-3d-e3.png" data-uri="/fouls/vs_bookings?division=4&start_season=8&end_season=23&highlight_teams[]=1&highlight_teams[]=6&highlight_teams[]=101&highlight_teams[]=91&min_match_count=190"></a>
  </figure>
</div>

The plots suggest that the Premier League has the least consistent refereeing of the top four leagues (r<sup>2</sup>: 0.20). League One and League Two have the most consistent, with r<sup>2</sup> values of 0.62 and and 0.55 respectively.

Whilst there may be other factors involved here, it’s not out of the question that the extensive media coverage of the Premier League impacts refereeing decisions. Mourinho could well be right again.

### Issues with this approach

Analysing fairness in this way is not perfect. Firstly, it only compares fouls and bookings: a relatively small part of the game. To obtain a more comprehensive picture of fairness, we’d have to analyse many more decisions, and determine whether each one went for or against a given team.

To pick topical example, in Chelsea’s recent clash with Liverpool, Mourinho felt aggrieved that Liverpool’s Lucas was not given a second yellow. Many pundits agreed, however this kind of decision won’t affect the results in this analysis, because the graphs only plot bookings given to Chelsea—not bookings that were not given to Chelsea’s opponents.

Secondly, the results may be affected by the fact that bookings are given out for offences <em>other than fouls</em> e.g dissent, simulation, or over-enthusiastic goal celebrations. I’d expect this effect to be even out over time, which is supported by the strength of the correlation in Figure 2. However the results may be skewed over short periods if, for example, a player gets frequently penalised for diving.

Thirdly, there is no indication on the graphs that the analysed matches may have been played in varying timeframes due to promotions, relegations, or extinctions. For example, Chester City only competed in the Football League between 2004-2010, but in Figure 2, their results are being compared against teams who have play from 2001-present. Given that rules and refereeing guidelines change, comparing teams in this way may not be totally satisfactory.

Despite these issues, I feel that the results give a reasonable indication of how teams are treated when it comes to receiving bookings. The Milton Keynes result is particularly noteworthy, and perhaps is worth exploring further.

## Summary

Since the beginning of last season, the stats indicate that there may be a Campaign Against Chelsea with regards to the number of bookings they’ve received. However Sunderland appear to have had the worst treatment of all league teams during this period.

The stats since 2000/2001 show that MK Dons have been given an outstandingly high number of bookings compared to the number of fouls they’ve committed. Southampton may be favoured by referees in this respect.

Finally, in terms of fouls and bookings, the Premier League seems to have the least consistent refereeing of the top four leagues. League One has the most consistent.

<footer class="post__footer">
  <p>Data: Copyright © <a href="http://www.football-data.co.uk">Football-Data.co.uk</a>. Retrieved Nov 10, 2015.</p>
  <ol>
    <li><a href="#footnote-1-link">☝︎</a> <a href="http://www.bbc.co.uk/sport/0/football/30618119" id="footnote-1">Jose Mourinho: There is a campaign against Chelsea</a>. Retrieved Nov 15, 2015.</li>
    <li><a href="#footnote-2-link">☝︎</a> <a href="http://www.bbc.co.uk/sport/0/football/34449753" id="footnote-2">Jose Mourinho: Chelsea manager charged with misconduct</a>. Retrieved Nov 15, 2015.</li>
    <li><a href="#footnote-3-link">☝︎</a> <a href="http://www-stat.wharton.upenn.edu/~waterman/Teaching/701f99/Class04/Notes/node4.htm" id="footnote-3">Standardized Residuals</a>. Retrieved Nov 15, 2015.</li>
    <li><a href="#footnote-4-link">☝︎</a> <a href="https://twitter.com/OptaJoe/status/616593147402035200" id="footnote-4">Lee Cattermole received 14 yellow cards in 2014/15</a>. Retrieved Nov 15, 2015.</li>
    <li><a href="#footnote-5-link">☝︎</a> <a href="https://en.wikipedia.org/wiki/Relocation_of_Wimbledon_F.C._to_Milton_Keynes" id="footnote-5">Relocation of Wimbledon F.C. to Milton Keynes</a>. Retrieved Nov 15, 2015.</li>
  </ol>
</footer>
