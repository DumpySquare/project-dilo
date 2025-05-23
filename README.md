
# Project Dilo

The idea of project dilo is to create a solution to support skydiving operations in exotic locations.  Key features include but not limited to, jump manifest, scheduling and announcements.  Additional functionality could inlude jumper profiles, to include personal information, emergency contacts, licensing (UPSA), insurance, passports, lodging information, number of jumps, ratings, tunnel time, preferred disciplines, friends, money, ...

## General architecture

### Website

A website is the first and easiest thing to accomplish.  Standard platform and user interaction.

This would require a back end to host information, and a front end to display everything.

I'm thinking a typical JS/TS back end service, with a website that would call APIs to display information

Basic setup, could be considered phase 1

- Pro's
  - simple architecture

- Con's
  - no offline access of information

### back end

Back end will be some sort of node.js (TS) based.  Support for websockets should be considered to provide real time updates.  Someone suggested NestJs

### database

Need to research options for long term storage.  JSON files is probably not the best.  First thought is MongoDB, but really open to anything.  the lighter the better.  I don't see any complex or large long term data storage needs.

### Mobile Apps (Andriod/IOS)

A more advanced solution would include mobile apps to support offline mode.  While information may not be the absolute latest, having some information could still be very useful

- Pro's
  - offline access

- Con's
  - more complicated

### Pages

- Login/account
  - Account creation can be based off of google, facebook or just email (stand-alone)
  - Account details
    - Full name
    - Alias
    - Age
    - exit weight
    - disciplines
      - belly, free fly, angle, track, wingsuite, flocking, event
    - number of jumps
    - total tunnel time
    - ratings and licenses (A, B, C, D, Pro, TI, Coach)
      - Could make this check boxes with input fields for license details
    - Gear details
    - Profile pic
    - Supporting pictures
      - Jump suites
      - Rig, helmet
      - canopy
      - gear bags
      - Cameras
      - This is mainly for identifying gear and helping to prevent loss
    - Friends (other accounts at the boogie)
      - Can help track down local people if needed
    - emergency contact information
    - Insurance details
    - Passport information
    - Hotel lodging
    - Vehicle (if applicable)
    - social media account inputs (facebook, instegram, ...)
    - email/phone
    - jumps purchased/used
    - last login
    - last 10 actions
      - update personal information, manifest for a jump, sign a waver, ...
    - Roles
      - Admin - master role, can manage money
      - Manifest role
        - sometimes they don't want jumpers to manifest
      - Staff (Manifest, Load organizers, Pilots, Medical, riggers, packers, TI)
        - This group can see all details
      - Jumper
        - This role can only see basic details of others
      - non jumper
        - friends and spouces not jumping but want to be a part of the group, schedule, chat, planning
- Main page (Intro/landing) page
  - main page describing the event and high level details
- Announcements
  - This page would host a list of announcements
  - Tie this into an alerts icon at the top of the screen (nav)
- Manifest
  - Virticle list of loads, load details, jumpers, jump type, jump group, ...
  - This could include backside rules to organize the load based on groups, jump types, and fall rates
  - base most information on Skydive Kapowsan
  - Jump vehicles and details
  - highlight the current jumper in manifest, and allow for search of what jumps a user is in
    - TI red, staff green, lo blue
- People
  - List of all people registered for the event, including staff, with pictures
  - mainly pulling details from each account
- Chat
  - Potential area for different jump groups, load organizing, picture/video sharing
  - Something like Microsoft teams with chat history and shared items
- Schedule
  - This could be something like other event apps
  - not full blown calendar (maybe)
  - but more of a day by day, hour by hour break down of the whole event
- Admin console
  - This is an admin page for admins to manage the event
  - include a log for seeing who is doing what
  - main page pic
  - boogie details
  - managing planes
  - reports?
    - Number of jumps?
    - cost per start
    - cost per jump run
    - flight telemetry?

## Phase 1

Phase 1 is purely focused on replacing the current spreadsheet solution

- loads
- jumper details

### requirements

- login
- user details
- loads

## Phase 2

Phase 2 could be more focused on an app with caching, schedule, chat and other expanded details for manifest and jumpers

## integrations

- UPSA?
  - Does UPSA have an api to access license details?
  - https://www.uspa.org/
- WindsAloft?
  - What are people using across the globe? (jump spot app?)
  - https://www.markschulze.net/winds/
  - https://aviationweather.gov/data/windtemp/?region=dfw&fcst=06&level=low
- Weather
  - Local weather, 24 hours and next 3 days
  - weather.com or wunderground.com?
- BurbleMe
  - Is there an API?
  - Can we access jumper information?
  - https://www.burblesoftware.com/tech-specs/3rd-party-integrations/
- smartwaver
  - https://www.smartwaiver.com/
  - https://api.smartwaiver.com/api/docs
- SpotAssist
  - https://www.spotassist.com/

## additional ideas

### Comms

- starlink
- peplink
  - multiple sim/esim + wifi bridging + ethernet wan with failover priorities
  - could also do wifi mesh to extend range

### app/notes

- run the app on a raspberry pi to keep the service local (minimize internet connectivity)
- cloud hosting
- supporting multiple languages
- need to consider how the site could be run long term
  - How do we handle multiple boogies?
  - How do we handle multiple boogies at the same time?
  - What do we do with old boogie information?
  - How do we distinguish between boogies if multiple at the same time?
    - FQDN?  or URL?  or cookie?
  - How do we manage the data structure?
    - do we base it around each "event"

## Emergency Details and Proceedures

- Country
- Country risks (political, geographical, environmental)
- Hospitals
  - Locations
  - Distances
  - Trauma support levels
- Evac
  - Jump plane, heli, jets to other countries
  - evac schedules and retainers
    - How busy are local evac resources?
    - Are they also ferring other passengers?
    - Are they dedicated and waiting for emergencies?
    - Are they on a retainer for the event?
- connectivity/notifications
  - How is cell service?
  - Do we need a sat phone?
  - GPS tracking
  - SOS beakon?

## possible project names

This sections is for brain storming terms for a product name.  Something unique that is related to the sport

project-dilo

short for dilotiko, greet for "manifest"

https://www.google.com/search?q=manifest+in+greek&sca_esv=ea28a01ba0d65b63&rlz=1C1WDIF_enUS1065US1065&sxsrf=AHTn8zrg6bK9NnVk3m5yhUmnlPcm9dz1ZA%3A1744360379885&ei=u9P4Z-PdNY-KhbIPyODmqQo&ved=0ahUKEwijp7bmyM-MAxUPRUEAHUiwOaUQ4dUDCBE&uact=5&oq=manifest+in+greek&gs_lp=Egxnd3Mtd2l6LXNlcnAiEW1hbmlmZXN0IGluIGdyZWVrMgoQABiABBhGGP8BMgUQABiABDIGEAAYFhgeMgYQABgWGB4yBhAAGBYYHjIGEAAYFhgeMgYQABgWGB4yBhAAGBYYHjIGEAAYFhgeMgYQABgWGB4yFhAAGIAEGEYY_wEYlwUYjAUY3QTYAQFI3DRQsgZYiC9wAngBkAEDmAHYBaABqjiqAQkzLTkuMy4yLjK4AQPIAQD4AQGYAg6gAtglqAIUwgIKEAAYsAMY1gQYR8ICDRAAGIAEGLADGEMYigXCAhMQLhiABBiwAxjRAxhDGMcBGIoFwgIKECMYgAQYJxiKBcICChAAGIAEGEMYigXCAgoQABiABBgUGIcCwgIHECMYJxjqAsICExAAGIAEGEMYtAIYigUY6gLYAQHCAg0QLhiABBhDGNQCGIoFwgIrEC4YgAQYQxjUAhiKBRiXBRjcBBjeBBjgBBj0AxjxAxj1Axj2Axj3A9gBAcICBRAuGIAEwgIIEAAYFhgKGB6YAwnxBdX_WjiCe2y4iAYBkAYKugYGCAEQARgBkgcHMi4zLTkuM6AHkaEBsgcFMy05LjO4B8El&sclient=gws-wiz-serp

### known terms for reference

Altitude, ditter, rig, parachute, helmet, elevation, plane, compass, gyroscope, vector, mirage, micron, firebird, tandem, Icarus



fun jump, 
spot assist

burbleme