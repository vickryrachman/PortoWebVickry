---
title: "Mining FMS Automation Validation"
date: 2026-06-18
draft: false
weight: 3
categories: ["Documents"]
tags:
  [
    "Fleet Management System",
    "Data Validation",
    "Root Cause Analysis",
    "Deviation Analysis",
    "Operational Reporting",
    "Mining",
    "Excel",
    "Google Sheets",
    
  ]
layout: "docs"
emoji: ":star_struck:"
url: "docs/fms-masa"
image: "/images/docs/fms-project.webp"
description: "Validated FMS automation accuracy against manual checker data through deviation analysis and weekly reporting."
---
## Role
 
Data Analyst
 
## Problem
 
A newly implemented Fleet Management System (FMS) at a mine site was designed to automatically calculate dump truck hauling trips. However, its accuracy had not been systematically validated against manual data from field checkers. Without structured validation, there was no way to know how reliable the FMS automation output was, where its biggest gaps were, or whether it was fit to serve as a basis for operational decision-making.
 
## Solution
 
Built a weekly data validation pipeline performing cross-validation across three simultaneous data sources: manual field checker reports, internal manual validation, and FMS automation output. Every discrepancy between sources was identified, classified by root cause type, and investigated through GPS playback and field verification. Validation results were compiled into structured weekly reports presented to the management team throughout a four-week trial period.
 
## Dataset Used
 
- Daily hauling trip data from 3 sources: manual field checker records, internal manual validation, and automated FMS output
- Trial data collected across 2 sites (referred to here as Site A and Site B) over a 4-week trial period
- Breakdown included: daily & weekly accuracy, accuracy per site, accuracy per truck category, product vs. non-product trip volume, GPS and trigger logs, and unit maintenance status
- Deviation case studies documented for each category — e.g., a suspected human-error case, a "ghost trip" case, a total GPS-signal-loss case, a unit signal-flicker case, and a trigger-log-error case

## Tools
 
- **Fleet telematics platform** — for GPS playback, trigger logs, and unit monitoring
- **On-unit FMS hardware** — dashcams, current/voltage sensors, GPS
- **Excel/Spreadsheet** — compiling manual trip records and standardized reporting templates
- **Looker Studio** — weekly dashboard for accuracy and deviation trend monitoring

## Analysis Process

![Data Cleaning ](FMSAnalysisWorkflow.png "Figure 1: Analysis workflow")
 
- Built a weekly validation pipeline that cross-validates data across the manual checker records, internal manual validation, and automated FMS output
- Classified deviations into 5 categories: Total GPS Off, Spatial/Partial Off, Ghost Trip, Unit Flicker, and Trigger Log Error
- Analyzed truck categories and sites separately, since deviation patterns and trip volumes differed significantly between segments
- Monitored accuracy at two levels in parallel, daily (fast anomaly detection) and weekly (improvement trend)
- Investigated each deviation via GPS playback and field verification, documenting representative case studies per deviation type
- Compiled results into a weekly report presented to the operations team

## Key Decisions
 
- **Five-category deviation classification** — Instead of simply logging deviations as "mismatched," each one is classified as Total GPS Off, Spatial/Partial Off, Ghost Trip, Unit Flicker, or Trigger Log Error. This lets the team prioritize fixes by root-cause type rather than raw deviation volume.
- **Separate validation by truck category** — Data is analyzed separately for the two truck categories based on haul type, since deviation patterns and trip volumes differ significantly between them. Combining them into one analysis would mask the distinct patterns in each category.
- **Parallel daily and weekly accuracy monitoring** — Accuracy is tracked at two granularities at once: daily for fast anomaly detection, weekly for improvement trends, giving the team both short-term and medium-term visibility in a single framework.
- **One case study per deviation type** — Each deviation type is documented with one representative case covering unit ID, material type, site, and investigation findings, turning aggregate data into a narrative the field and management teams can act on.

## Key Insights
 
- FMS automation accuracy improved dramatically from 3% in week 1 to 72% in week 4 through iterative fixes based on validation findings
- By the final week of the trial, manual validation accuracy against the reference target reached 86%, with a 9-percentage-point gap remaining to the 95% target
- Accuracy differed significantly between sites: Site A at 89% vs. Site B at 99%
- The dominant issues were trucks detected as spatially off-route and fully off-GPS (both spiking mid-trial), while "ghost trip" indications only emerged in week 4
- 37 units were flagged for urgent maintenance; by the end of the trial, 18 had been completed and 1 remained pending
- In the first two months of implementation, hauling deviation decreased by 3% and safety violations decreased by 30%

## Recommendations
 
- Standardize geofencing boundaries at the lower-accuracy site (Site A), following the practices that helped Site B reach 99% accuracy.
- Follow up promptly on the remaining flagged unit still awaiting maintenance, and schedule routine preventive maintenance for all flagged units.
- Develop a specific procedure for the newly emerging "ghost trip" deviation category so it doesn't recur in future periods.
- Formalize this weekly validation framework as a standard ongoing process, while continuing to push accuracy toward the 95% target.
 