# 구현해야할 요청들

## api 전체 구조
```
├─ news
|  └─ get
|     ├─ /news/notices # searchText, type
|     └─ /news/events
├─ characters
|  └─ get
|     └─ /characters/{characterName}/siblings
├─ armoires
|  └─ get
|     ├─ /armories/characters/{characterName}/profiles
|     ├─ /armories/characters/{characterName}/equipment
|     ├─ /armories/characters/{characterName}/avatars
|     ├─ /armories/characters/{characterName}/combat-skills
|     ├─ /armories/characters/{characterName}/engravings
|     ├─ /armories/characters/{characterName}/cards
|     ├─ /armories/characters/{characterName}/gems
|     ├─ /armories/characters/{characterName}/colosseums
|     └─ /armories/characters/{characterName}/collectibles
├─ auctions
|  ├─ get
|  |  ├─ /auctions/options
|  └─ post
|     ├─ /auctions/items
├─ guilds
|  └─ get
|     ├─ /guilds/rankings
├─ markets
|  ├─ get
|  |  ├─ /markets/options
|  |  ├─ /markets/items/{itemId}
|  └─ post
|     ├─ /markets/items
└─ gamecontents
   ├─ /gamecontents/challenge-abyss-dungeons
   ├─ /gamecontents/challenge-guardian-raids
   └─ /gamecontents/calendar
```

## api 활용 구조 예시
```
from riotwatcher import LolWatcher

lol_watcher = LolWatcher('<your-api-key>')

# use v4 explicitly
matchlist = lol_watcher.lol_status_v4.platform_data('na1')

# use v3 explicitly
old_matchlist = lol_watcher.lol_status_v3.shard_data('na1')
```