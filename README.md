# mline -- Tokyo Metro Lines

Search your route.

```
   ./bin/mline 神保町 三田 -l 3
神保町 -> 三田 [三田線]
神保町 -> 大手町 [半蔵門線] -> 三田 [三田線]
神保町 -> 押上 [半蔵門線] -> 三田 [浅草線]
Found 3 routes.
```

```
   ./bin/mline 神保町 神保町 -l 3
神保町
神保町 -> 九段下 [半蔵門線] -> 神保町 [新宿線]
神保町 -> 大手町 [半蔵門線] -> 神保町 [三田線]
神保町 -> 住吉 [半蔵門線] -> 神保町 [新宿線]
神保町 -> 大手町 [三田線] -> 神保町 [半蔵門線]
神保町 -> 九段下 [新宿線] -> 神保町 [半蔵門線]
神保町 -> 住吉 [新宿線] -> 神保町 [半蔵門線]
Found 7 routes.
```

## lines.json

All supported lines and its stations are described in `lines.json`.
