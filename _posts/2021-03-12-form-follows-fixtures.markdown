---
layout: post
date: 2021-03-11
title:  Form Follows Fixtures
description: ""
og_image:
tags:
---

Teams play eachother just twice in a season, which statistically speaking, may not be enough to determine whether one team is significantly better than another. Managers come-and-go, players get injured or are transferred, and along with countless other factors, mean that teams go in-and-out of form. Given the relatively small number of games played, is it possible that one team may have an easier set of fixtures than another? Could this have an impact on the final league standings?

## Opponent Form Points

To explore the effect of a fixture set on the result of an individual match, we'll introduce **opponent form points** (OFPs). This is determined by taking a fixture played by a given team, then calculating the points won by the opponent in their previous five league games.

<table class="results breakout-right">
  <caption>
    <span class="figure-number">Figure 1.</span>
    OFP for Liverpool's match vs. Man Utd
    <span class="subheading">i.e. Man Utd's previous 5 results</span>
  </caption>
  <thead>
    <th></th>
    <th></th>
    <th></th>
    <th></th>
    <th></th>
    <th></th>
    <th class="points"><abbr title="Points won by Man Utd">Pts</abbr></th>
  </thead>
  <tbody>
    <tr class="result result--draw">
      <td class="date">2 Oct</td>
      <td class="home-team">Man Utd</td>
      <td class="home-team-goals">1</td>
      <td class="goals-separator"></td>
      <td class="away-team-goals">1</td>
      <td class="away-team">Stoke</td>
      <td class="points">1</td>
    </tr>
    <tr class="result result--win">
      <td class="date">24 Sep</td>
      <td class="home-team">Man Utd</td>
      <td class="home-team-goals">4</td>
      <td class="goals-separator"></td>
      <td class="away-team-goals">1</td>
      <td class="away-team">Leicester</td>
      <td class="points">3</td>
    </tr>
    <tr class="result result--loss">
      <td class="date">18 Sep</td>
      <td class="home-team">Watford</td>
      <td class="home-team-goals">3</td>
      <td class="goals-separator"></td>
      <td class="away-team-goals">1</td>
      <td class="away-team">Man Utd</td>
      <td class="points">0</td>
    </tr>
    <tr class="result result--loss">
      <td class="date">10 Sep</td>
      <td class="home-team">Man Utd</td>
      <td class="home-team-goals">1</td>
      <td class="goals-separator"></td>
      <td class="away-team-goals">2</td>
      <td class="away-team">Man City</td>
      <td class="points">0</td>
    </tr>
    <tr class="result result--win">
      <td class="date">27 Aug</td>
      <td class="home-team">Hull</td>
      <td class="home-team-goals">0</td>
      <td class="goals-separator"></td>
      <td class="away-team-goals">1</td>
      <td class="away-team">Man Utd</td>
      <td class="points">3</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <th colspan="6">Total (OFP)</th>
      <td class="points">7</td>
    </tr>
  </tfoot>
</table>

For example, let's go back to Liverpool vs. Manchester United in October 2016 (Figure 1). United's results prior to that fixture were two wins and a draw, giving an OFP of 7.

## Analysis

First, we'll establish whether an opponent's form has an impact on the result of a match i.e. whether it is indeed harder to get a result against an in-form team versus an out-of-form one. We can do this by examining the probabilities of winning, losing, or drawing for each OFP value. Figure 2 plots these relationships, covering matches in all leagues between 2007/08 to 2016/17.

<figure class="breakout">
  <h3>
    <span class="figure-number">Figure 2.</span> Opponent Form Points vs. Probabilities of Winning, Losing, and Drawing <span class="subheading">covering matches between 2007/08 and 2016/17 inclusive</span>
  </h3>
  <img src="/assets/form-follows-fixtures/fig-2.png" data-uri="/forms/vs_result_probability?team=&division=&start_season=15&end_season=24">
</figure>

Unsurprisingly, the more points your opponent has picked up in their previous five games, the more likely you are to lose, but this graph also highlights some pretty nice symmetry. The probabilty of drawing is about 0.26, regardless of the opponent form. The likelihood of _losing_ against a team with no points in their previous five games, is roughly the same as beating a team with a perfect record, which is also about the same as the probability of drawing with them. What's more, the chances of _beating_ a team with no points in their previous five games, is approximately the same as losing to a team with a perfect win record.

### Predicting Expected Points

We can develop this further by looking at the relationship between OFP and mean points scored. Figure 3 plots this relationship, as before, covering matches in all leagues between 2007/08 to 2016/17. (Fixtures where the opponent played fewer than five games have been disregarded so that the OFP calculation is based on the same number of matches.)

<figure class="breakout">
  <h3>
    <span class="figure-number">Figure 3.</span> Opponent Form Points vs. Avg. Points Won per Match <span class="subheading">covering matches between 2007/08 and 2016/17 inclusive</span>
  </h3>
  <img src="/assets/form-follows-fixtures/fig-3.png" data-uri="/forms/vs_points?team=&division=&start_season=15&end_season=24">
</figure>

As we'd expect, there is a negative correlation: the more points your opponent has won leading up to your fixture, the fewer points you are likely to win. In the extreme cases, you're likely to win ~0.65 points more per game playing a team who has lost all their previous five matches than if you played a team with a perfect win record. This equates to about 2 extra points every three games.

It is of course very unlikely that a team's run of fixtures will only include entirely in-form, or entirely out-of-form teams, but given the strong negative linear correlation, we can use the equation of the trendline to predict the points a team is expected to win based soley on their opponent's form.

For example, with the Liverpool versus Man Utd fixture, the OFP was 7. According to the chart above, Liverpool could be expected to win about 1.4 points.

Taking this a step further, we can predict the expected points (xP) each team should win across an entire season, and therefore infer whether opponent form plays a significant role in the final league standings.

### Case 1: Man City/Man Utd Premier League 2011/12

First we'll look at the tightest top-flight finish in recent years: the 2011/12 season when Man City pipped Man Utd to the league title on goal difference on a dramatic final day of the season.

Figure 4 displays OFPs as bars for every fixture in that season. The height and darkness of the bar reflects the magnitude of the OFPs, with the result of the match show below: <strong style="color: #238023">green</strong> for a win, <strong style="color: #707070">grey</strong> for a draw, and <strong style="color: #d42626">red</strong> for a loss. Hover over a row or a bar for more detailed information. It is ordered by the mean OFP, lowest first, so the team at the top had the easiest run of fixtures, whereas the team at the bottom had the hardest. For improved accuracy, the xP calculation has been based on 10 seasons of Premier League matches up-to-and-including 2011/12 (`Y = -0.06X + 1.75`).


<figure class="breakout">
  <h3>
    <span class="figure-number">Figure 4.</span> Opponent Form Points for every Fixture <span class="subheading">covering matches in the 2011/12 Premier League season</span>
  </h3>
  <iframe width="770" height="689" src="/assets/form-follows-fixtures/fig-4.html"></iframe>
</figure>

If Man City's fixtures played a significant role in them winning the title, we'd expect them to be placed towards the top of this table, some distance from their rivals, particularly Man Utd. As it turns out, Man City had the 4th hardest fixture set (xP: 51.08), a little harder than that of Man Utd's (xP: 51.68).

Despite there being a ~3.5 point difference between the easiest and hardest fixture set, in this instance, none of the xP differences would have caused a change in the key league positions i.e 1st, 4th (Champions League spot), 5th (Europa League) and 17th (relegation).

The following cases look into situations where the fixture set may have played a significant part in the final league standings. Data was analysed from all domestic leagues, from 2012/13 to 2016/17.

### Case 2: Arsenal/Tottenham Premier League 2012/13

Arsenal needed to overturn a 7 point deficit in their last ten games to ensure they beat their North London rivals to Champions League qualification. They managed to do so, finishing just 1 point above Tottenham. However, according to OFP/xP calculations, Arsenal had the second easiest set of fixtures (xP: 52.22), whereas Tottenham had the hardest (xP: 49.64)—a significant difference of 2.58 points.

<p>
  <small>Calculation based Premier League matches from 03/04-12/13 inclusive:<br>
    <code>Y = -0.06X + 1.72</code><br>
    <code>r² = 0.94</code><br>
    <a href="/assets/form-follows-fixtures/case-2.html">View OFP table</a>
  </small>
</p>

### Case 3: Birmingham/Doncaster Championship 2013/14

Birmingham entered the final day of the 2013/14 Championship season in the relegation zone, just 1 point from safety behind Doncaster. However, it wasn't looking hopeful as they were 2-0 down at Bolton in the final game with just 14 minutes remaining. They managed to claw it back to 2-2 in added time, whilst Doncaster lost 1-0 at Leicester.

Doncaster had the toughest run of fixtures (xP: 59.71); Birmingham's was the fourth easiest (xP: 61.15). This 1.44 point difference could've been crucial as Doncaster were relegated on goal difference.

<p>
  <small>Calculation based Championship matches from 04/05-13/14 inclusive:<br>
    <code>Y = -0.03X + 1.51</code><br>
    <code>r² = 0.61</code><br>
    <a href="/assets/form-follows-fixtures/case-3.html">View OFP table</a>
  </small>
</p>

### Case 4: Middlesbrough/Brighton Championship 2015/16

Middlesbrough and Brighton were both fighting for automatic promotion to the Premier League, and coincidently met eachother on the final day of the season at the Riverside. Brighton needed a win; Middlesbrough just a draw. The match ended 1-1 following a questionable Mike Dean red card against Brighton.

Middlesbrough had the fourth easiest fixture set (xP: 63.16), whereas Brighton had the hardest (xP: 62.08). As before, that 1.08 point difference could've been significant as Middlesbrough were promoted on goal difference. (As a Brighton fan, this still hurts a little.)

<p>
  <small>Calculation based Championship matches from 06/07-15/16 inclusive:<br>
    <code>Y = -0.02X + 1.49</code><br>
    <code>r² = 0.46</code><br>
    <a href="/assets/form-follows-fixtures/case-4.html">View OFP table</a>
  </small>
</p>

### Case 5: Newcastle/Brighton Championship 2016/17

Brighton secured automatic promotion to the Premier League with three games to spare, needing only a further 3 points from the remaining fixtures to guarantee the title. After some pretty wild celebrations and conceding two freak own-goals against Norwich, they only managed a point, and Newcastle went on to clinch the title. (Yes, this hurts, too.)

For the second year running, Brighton had one of the toughest fixture runs (xP: 60.51). Newcastle didn't have a particularly easy run (eleventh easiest, xP: 61.53), but that extra point _could've_ been crucial. (Newcastle did have a superior goal difference, so it might not have mattered, but given that this model does not consider goals scored or conceded, opponent form may have had an impact.)

<p>
  <small>Calculation based Championship matches from 07/08-16/17 inclusive:<br>
    <code>Y = -0.03X + 1.53</code><br>
    <code>r² = 0.73</code><br>
    <a href="/assets/form-follows-fixtures/case-5.html">View OFP table</a>
  </small>
</p>

## Problems with this Approach

It's worth emphasising that this is obviously not a complete or accurate xP model. The range of xPs is limited since it only examines a single variable. Rather than to produce an absolute points prediction, the aim is to look at relative points differences to determine significant outcomes.

There are also issues with how form is evaluated. OFPs are calculated using points, which is a naive measure of performance. One team might outplay another yet still lose. What's more, points give equal weight to a narrow win as to a convincing one. Perhaps a better measure of performance would be to work with expected goals (xG), expected goal difference (xGD) or even simply goal difference.

The model also only looks at _opponent_ form. To improve the model, it might be worth exploring the form of both teams, as well as other factors such as home advantage.

## Summary

We've established that summing an opponent's points from their previous five games is a reasonable indicator of fixture difficulty. By tabulating opponent form points for each team across a season, we can gauge which teams had harder or easier fixture sets; and using a basic model, determine potentially significant points differences.

The expected points difference between the hardest fixture set and the easiest is typically around 1-3 points. For this to have an impact on important league standings (e.g. 1st place or promotion/relation spots), rivals would need to be close in terms of actual points, _and_ be at opposing ends of of the opponent form table. This is pretty rare, although there are a few seasons where opponent form may have played a part.
