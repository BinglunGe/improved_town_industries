# Improved Town Layouts

## Changelog

### 1.01 (hotfix)
- Changed low-density shops to nearly always appear in a town, to accept food and goods and avoid a chicken-and-egg-problem with citybuilder scripts which require food or goods to grow towns.
  - Now available 1700-9999, Probability 15 (maximum), limit 1 per town.

- Removed in 1.02 ~~Added support for ECS Tourists (cargo label TOUR)~~
  - ~~Accepted by: Old Church, Neo-Moorish Church, Stadium (new and old), Hotel, Theatre, Nakagin Capsule Tower.~~
  - ~~Future update will let these buildings generate tourists, once I figure out the cargo_production callback.~~

### 1.02
- Added population requirements for stadiums
  - Old stadium has a minimum of 1,000 people
  - Modern stadium has a minimum of 10,000 people
  - Towns can now have both types of stadiums
- Town buildings no longer accept ECS Tourists
  - This was improperly implemented and needs revision.
 
### 1.03
- Default houses are now overridden in all climates.

### 1.1.0
*Not savegame compatible.*
- Feature: Improved Mail changes residential buildings to produce nearly no mail, while slightly increasing mail from commercial buildings
- Add: Option to reuse Bank (both temperate and sub-arctic/sub-tropical) and sub-arctic Hotel sprites as University, Courthouse, and Spa, respectively. Must be activated in Parameters to avoid conflicts with industries which use the same sprites (Banks in vanilla industry, Hotel in FIRS).
- Add: Museum, which builds overlooking water to the southwest
- Add: Parameter to enable/disable sub-tropical sprites (default = disable)
  - Neo-Moorish Church
  - Concrete warehouse
- Change: Modern office buildings now need ~600 residential population per building, down from 1,000
- Change: Hotels and Spas only build in cities
- Change: Residential buildings no longer build next to office buildings
  - Makes office districts more concentrated
  - Town Houses and Houses: within 2 tiles
  - Small Flats: within 1 tile if passenger service provided
  - Small Flats: no restriction if no passenger service provided, to avoid gaps on the perimeter of office districts
- Change: Small Flats now available in town centres
- Change: Swapped some Flats, Small Flats, and Town House sprites around
  - Flats are now high-density housing, Small Flats are medium-density requiring passenger service, Town Houses are low density (but allowed in town centres), and Houses are low-density and not allowed in town centres
- Change: Tube-style office building no longer spawns
  - Still available in savegames, but won't build new
  - Reason? I think it looks silly
- Change: Markets spawn more often
  - No longer restricted by location away from houses
  - One market allowed per town
- Fix: All buildings now appear above snowline in Sub-Arctic climate
  - An error now appears in the NewGRF window warning players that this set does not support snow sprites
- Fix: Market building no longer appears to hover or flicker
- Fix: Cinema and Theatre buildings now match their ground tiles when using aBase
- Fix: Version numbering now uses 0.0.0 style instead of 0.00
- Fix: Version number now appended to NewGRF name in NewGRF window

### 1.1.1
- Add: Error message when trying to use Improved Town Layout with a version of OpenTTD which is too old (requires 1.10.0, JGR 0.34, or better)
- Add: Makefile for code compilation
- Change: Break up code from one huge NML file to several NML files for easier editing
- Change: Organize file structure
- Fix: Land below parks, statues, and fountains can be lowered again (#4)