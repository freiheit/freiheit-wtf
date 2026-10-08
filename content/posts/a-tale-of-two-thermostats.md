---
title: A Tale Of Two Thermostats
description: "Adventures with Home Assistant"
date: 2026-10-30T22:00:00.000Z
preview: ""
draft: true
tags: [home-assistant, home-automation, automation, home, home-ownership]
categories: []
---

## The House

2 years ago, I inherited enough money for a downpayment and my partner and I
bought a house.

Our house is 2 stories, with separate thermostats for the upstairs and
downstairs. One of the first purchases was replacing the original
thermostats with new "smart" thermostats.

The furnace has baffles or something so that when one thermostat is
requesting heat it only sends warm air to that area, and when both
thermostats request heat it runs the fan and gas and stuff at a higher
setting and pushes hot air everywhere.

But we eventually discovered that the AC is older and can only run or not
run and so when either thermostat requests cold, all it can do is push cold
air to the entire house.

And as an added bonus, the room we decided would be my home office is
upstairs on the west side of the house, so tends to be the warmest in the
house.

## The Thermostats

They're ecobee smart thermostats:

- a couple wireless sensors (heat and presence-detection) per thermostat
- know our rate plan with the power company, so can do stuff like "pre-cool"
  the house ahead of higher late afternoon rates on hot days.
- and connected to a power company API where the power company can request
  scheduled load-shedding and our thermostats will do the same pre-cool and
  then higher setpoint thing for those. There's also some short-notice ones
  it can respond to.
  - power company gives us a small discount just for having thermostats
    connected to that API, and a bigger discount when we actually reduce
    power usage during the load-shedding request windows.

## The Problem

Temperature Imbalance

On a hot day with the AC set to 72 upstairs, the office will be 76 or 78

## Plan A

We had Amazon Echo/Alexa stuff connected
