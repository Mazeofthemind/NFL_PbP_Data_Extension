# NFL_PbP_Data_Extension
## Introduction
Charting of NFL plays (recording offensive/deffensive situations, behaviors and outcomes) is an essential preresquisite of quantitative analysis.
Many observers assume that a shortage of semi-skilled labor is the primary reason that advanced charting is not broadly available for all teams and games.
In reality, the open source community expends 100s of man hours analyzing approxomately 263 hours of regular season game tape, yet produce a sparse, inconsistent charting that is difficult to combine across annotators.
Methodologies to produce complete, consistent charting across annotators of varying interests, skills and experience are a core competency of high performing NFL frnachises and sports analytics firms (a la PFF).

This project attempts to address some of these challenges by providing that documentation, tooling and methodology to produce more detailed, consistent and reusable open source data.

# Defensive Composition, Alignment and Action
Describing a defense's composition (active players and roster positions), alignment (formation and implied positions) and plan of execution (demonstrated coverage) for the purposes of analytics is challenging.

## Defensive Composition
Defensive composition describes the players active during a play and their role on the field by way of their positions on the field. This information takes the form of an annotated list 

ndividual defensive players on the field, their rostered positions and their positions on the field

Annotating the players 

Assuming that a consolidated team roster is available (list of all active players for that team in that season with numbers, assuming no reuse), this data can be captured in a simple unordered list of integers (player numbers)

## Defensive Alignment/Front
Defensive alignment describes the positioning of the defense on the field (collectively and individually) in ways that are theoretically predictive of player role.
This information is much more difficult to describe then composition because is subjective, relying on arbitrary ways of dividing the defensive personnel and describing archetypes within those divisions.

This is further complicated by the many notations available for describing defensive alignment, and their tendency to be designed for the benefit of offensive players making on-field decision related to their individual responsibilities, rather then compactly or precisely describing the defense as a hole. It also requires at least a limited amount of post-snap observation due to the tendency of DC to blur or outright disguise actual defensive alignments before the snap.

https://www.xandolabs.com/index.php?option=com_content&view=article&id=917:27protocols-for-a-defensive-identification-system&catid=99&Itemid=163

For ease of notation and processing this suggests the numeric approach of dividing  the defense into (rough) levels from the line, line backers, safeties and defensive backs 3-4-2-3. It must be acknowledged that this loses information inherent in more complicated, field localized description approaches which look at individual player alignment versus the OL to gain additional predictive power on player roles.

Currently alignment must be determined from film analysis, however in the future it may be inferred from 2D field positioning data, which is arguably more useful and precise

## Defensive Movement
Against running plays, defensive movement and role is fairly straightforward, with the entire defense converging from various positions to the LOS. Pass plays require much more sophisticated forms of defensive movement because every eligible pass catcher can become a potential threat.

To some degree defensive movement can be identified from alignment, but DCs are highly incentivized to minimize that predictive relationship, so it is almost always necessary to observe defensive movement briefly after the snap.

http://insidethepylon.com/film-study/film-study-nfl/defense-film-study-nfl/2014/09/10/understanding-pass-defenses/
