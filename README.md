# mline -- Tokyo Metro Lines

Search your route.

```bash
$ ./bin/mline <from-station> <to-station>

$ ./bin/mline 神保町 神保町
神保町 -> 大手町 [半蔵門線] -> 神保町 [三田線]
神保町 -> 大手町 [三田線] -> 神保町 [半蔵門線]
神保町 -> 九段下 [新宿線] -> 神保町 [半蔵門線]
神保町 -> 九段下 [半蔵門線] -> 神保町 [新宿線]
Found 4 routes.
```

## Options

```bash
$ ./bin/mline -h
Usage: mline [options]
    -l INT                           Upper the route length (num of stations) (default: 4)
    -w INT                           Weight of train-change (default: 4)
    -m, --margin INT                 このくらいなら遅くても許す
    -F, --jr                         Allow fucking JR lines
```

### `-m, --margin`

BFS で基本的には距離の短いルートから順に探索して表示する.
`--margin` が 0 のときは完全にそうで、ここに正の整数を指定すると、その分くらい距離が遠回りでも探索に入れる.
デフォルトは 1.

### `-w` 距離関数

一つの路線で A 駅から B 駅までの距離は、その間に通る駅の個数+1.
乗り換えをする場合、乗り換え一回について、そこに `w` だけ加える.
`w` が大きいほど、乗り換えをできるだけしないルートを探す.
小さいほど、乗り換えしてでも間にある駅数の少ないルートを探す.
デフォルトは 2.

山手線は駅数ばっかり多いから注意.

### `-F, --jr`

mline は本来メトロのためのものだけど、関係あるだろう中央線と総武線と山手線は、いま `lines.json` に入ってる.
デフォルトでその路線は使わないが、このオプションを指定したときだけ、有効になる.

```bash
$ ./bin/mline 恵比寿 渋谷
恵比寿 -> 六本木 [日比谷線] -> 青山一丁目 [大江戸線] -> 渋谷 [銀座線]
恵比寿 -> 六本木 [日比谷線] -> 青山一丁目 [大江戸線] -> 渋谷 [半蔵門線]
Found 2 routes.

$ ./bin/mline -F 恵比寿 渋谷
恵比寿 -> 渋谷 [山手線]
Found 1 routes.
```

山手線を使っちゃうと距離 1 で行けることになるので `--margin` で大きい数字を指定しないと他のルートを探索しなくなる.

## lines.json

All supported lines and its stations are described in `lines.json`.
