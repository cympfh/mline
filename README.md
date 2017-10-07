# mline -- Tokyo Metro Lines

Search your route.

```
   time ./bin/mline 神保町 三田
神保町 -> 三田 [三田線]
神保町 -> 神保町 [半蔵門線] -> 三田 [三田線]
神保町 -> 大手町 [半蔵門線] -> 三田 [三田線]
神保町 -> 押上 [半蔵門線] -> 三田 [浅草線]
神保町 -> 神保町 [新宿線] -> 三田 [三田線]
Found 5 routes.
./bin/mline 神保町 三田  0.05s user 0.01s system 95% cpu 0.058 total
```

```
   mline 神保町 神保町
神保町 -> 九段下 [半蔵門線] -> 神保町 [新宿線]
神保町 -> 大手町 [半蔵門線] -> 神保町 [三田線]
神保町 -> 住吉 [半蔵門線] -> 神保町 [新宿線]
神保町 -> 大手町 [三田線] -> 神保町 [半蔵門線]
神保町 -> 九段下 [新宿線] -> 神保町 [半蔵門線]
神保町 -> 住吉 [新宿線] -> 神保町 [半蔵門線]
Found 6 routes.
```

## lines.json

All supported lines and its stations are described in `lines.json`.
