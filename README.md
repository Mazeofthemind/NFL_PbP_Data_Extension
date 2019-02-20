# NFL Play by Play Charting Extensions

1. [Introduction](#introduction)
2. [Defense](#defense)
3. [Offense](#offense)

## Introduction

Detailed charting of NFL plays (recording offensive/defensive situations, behaviors and outcomes) is the essential prerequisite of quantitative analysis.

This is why detailed charting is considered a core competency and competitive advantage by NFL franchise analytics departments and private analytics (ex. PFF).

Basic play-by-play charts are already available freely to the public via the NFLs public API. This data includes basic information which generally focuses on the key players and outcomes of the offensive and defensive halves of a player.

That said, this charting excludes large amounts of offensive and defensive information which is necessary for deeper analysis.

Every year the open source analytics community expends 100s of volunteer hours 
building additional charting for 263+ hours of NFL game film.
In theory this should be more then enough to produce high quality charting for every NFL game if done efficiently, but in reality produces very little in the way of publically accessible and usable data.

This project attempts to address the challenge of transforming this volunteer labor into high quality data requires a combination of documentation, software tooling and methodologies which will allow them to produce accurate and reusable expanded charting.

# Components of Offensive and Densive Charting

## Player Composition/Alignment

Player Composition and alignment describes the initial state of the offense and defense in a way which allows us to understand the players involved (beyond the ball handlers and tacklers recorded in the NFL play-by-play) and probable offensive and defensive strategy.

Charting composition is simple and identical for both offense and defense, listing the players on the field using the NFLs player ID system.
The NFL ID is used in place of the player's name and jersey number in order to disambiguate the player without relying on the team's roster for that season.

Alignment attempts to provides offensive (TE, WR) and defensive (S, OLB) labels which provide information on the presumed role of the player based on their relative location on the field 

### Positional Subjectivity
How far does a TE need to be from the OT to become a slot WR?) and finding a 

### Positional Abstraction
useful level of abstraction that works consistently across all plays (do we describe players as WR or X/Y/Z recievers)

##Subgroup Organization

Even once we have described the broad composition and alignment of the offense or defense, there is still important information to be captured about specific subgroups.

Describing that there are 3 WR on the field fails to describe where they are relative to the OL/QB (which are required to be fixed). 

## Movement
In reality player movement on the team is extremely complex when described in its full detail (such as the NFLs next gen motion capture). 
It is far more useful to identify patterns in typical offensive and defensive movement, name them

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