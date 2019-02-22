# NFL Play by Play Charting Extensions

1. [Introduction](#introduction)
2. [Defense](#defense)
3. [Offense](#offense)

# Introduction

Consistent, detailed charting is an essential part of developing powerful analytics and insights. It is considered a key asset for NFL franchises and private firms which can either purchase or produce it.

Meanwhile the open source analytic community must rely on the basic play-by-play (PBP) charting available via the NFLs public API, and augment where needed with hand crafted charting.
This hand crafted charting adds up to 100s of hours across the community, concentrating on approxomately 263+ hours of game film.

While in theory this should be more then enough labor to produce free, high quality supplementary data to the NFL PBP if employed effectively. 
In reality public supplementary data is sparse to nonexistent for most games and teams, even within the open source analytics community.

This project attempts to provide documentation, tooling and methodologies to help the open source community maximize the efficiency of its voluntary charting in order to provide high quality supplementary PBP to the community.

# Components of Offensive and Defensive Charting

*Please note that this guidance represents just one way to describe a football offense and defense in the course of a play. Countless terminologies and methdologies exist across various analysts, this is essentially a synthesis of several which attempts to maximize flexibility and descriptiveness*

## Positional Composition/Alignment

Player **Composition and Alignment** attempts to describes the state of the offense/defense before a play in terms of players and their responsibilities.
This data is not included in NFL PBP other then those who happen to handle the ball (usually no more then 3-4 on any given player)

**Composition** is the simpler of the two descriptive techniques and includes two basic data artifacts: 

1. **Composition Identifier** (in numeric shorthand) describing the mix of positions on the field for the offense or defense (ex. 3-1-1 for offense)
2. **Player IDs** in a predetermined order that signifies their **Position on the Field** (potentially opposed to rostered position) within the composition (ex. 7th ID is the leftmost WR on a 3-1-1 offense). 

##Positional Formations
Once the **Composition Identifier** establishes the size of each position group, we must still describe the placement or **Positional Formation** of its members.

For example, 3 WR have drastically different responsibilities when deployed in *3-0 Loose Bunch* (3 WR bunched to the right) as opposed to a *2-1 Spread* (2 outside WR and one slot WR to the left).
Similar variations are possible for the defensive line (4 Bear) and defensive backfield (Cover 2)

Compared to **Composition** the terminology and classification of formations is extremely variable and subjective. 

## Individual Action
Once we have identified the **Composition** and **Formation** of each position group, we must still account for the significant actions that those groups take after the snap.

Different actions demand different levels of detail

Some, like *Coverage*, *Rushing*, *Blocking" can be described by simple one-world labels

Others require longer, more detailed definitions like WR routes (short, deep curl, slant, etc.) and pass attempts (rollout) 

## Player Performance Charting
In addition to providing detailed descriptions of individual actions, we can provide additional descriptive detail on the outcome of those actions

For offensive plays and defensive plays involving the movement of the ball, yards and possession, they can be described as 

Passing plays, for example, give us an opportunity to judge the accuracy of the QB, the separation, hands and run-after-catch ability of the WR and the coverage of the DB.

All plays involve blocking for many or most of the players on the field, providing another grading opportunity both individually and collectively

Offensive line play as a collective unit can be 

Obviously performance is among the most subjective and position sensitive attribute in this extension framework, and will have the most room for dissent among annotators.

# Offense

## Subgroup Organizations

### Running Backs

To some degree these subgroups also required a set number of running backs, or 

Some of these alignments predicate a specific number of running backs, . Additionally they must be translated to the QB alignment (under center, pistol, shotgun) as well.

https://www.dummies.com/sports/football/offense/footballs-offensive-team-formations-for-running-backs/
# Defense

Describing a defense's composition (active players and roster positions), alignment (formation and implied positions) and plan of execution (demonstrated coverage) for the purposes of analytics is challenging.

## Defensive Composition
Defensive composition describes the individual defensive players on the field and their rostered positions. This information is non-subjective (unlike most other defensive data) but bulky and complicated to notate compared to the other defensive data described here, and poorly predictive of actual role on the field given the tendency of the NFL to put players outside their rostered position.

Assuming that a consolidated team roster is available (list of all active players for that team in that season with numbers, assuming no reuse), this data can be captured in a simple unordered list of integers (player numbers)

## Defensive Alignment/Front
Defensive alignment describes the positioning of the defense on the field in ways that are theoretically predictive of player role. This information is much more difficult to describe then composition because is subjective, relying on arbitrary ways of dividing the defensive personnel and describing archetypes within those divisions.

This is further complicated by the many notations available for describing defensive alignment, and their tendency to be designed for the benefit of offensive players making on-field decision related to their individual responsibilities, rather then compactly or precisely describing the defense as a hole. It also requires at least a limited amount of post-snap observation due to the tendency of DC to blur or outright disguise actual defensive alignments before the snap.

https://www.xandolabs.com/index.php?option=com_content&view=article&id=917:27protocols-for-a-defensive-identification-system&catid=99&Itemid=163

For ease of notation and processing this suggests the numeric approach of dividing  the defense into (rough) levels from the line, line backers, safeties and defensive backs 3-4-2-3. It must be acknowledged that this loses information inherent in more complicated, field localized description approaches which look at individual player alignment versus the OL to gain additional predictive power on player roles.

Currently alignment must be determined from film analysis, however in the future it may be inferred from 2D field positioning data, which is arguably more useful and precise

## Defensive Movement
Against running plays, defensive movement and role is fairly straightforward, with the entire defense converging from various positions to the LOS. Pass plays require much more sophisticated forms of defensive movement because every eligible pass catcher can become a potential threat.

To some degree defensive movement can be identified from alignment, but DCs are highly incentivized to minimize that predictive relationship, so it is almost always necessary to observe defensive movement briefly after the snap.

[](http://insidethepylon.com/film-study/film-study-nfl/defense-film-study-nfl/2014/09/10/understanding-pass-defenses/)




# Installation
Software uses play by play data imported from the NFLScrapR project  https://github.com/ryurko/nflscrapR-data/tree/master/play_by_play_data