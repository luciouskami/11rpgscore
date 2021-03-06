# 11平台RPG积分教程
# by actboy168
*RPG积分*是11平台新推出的积分，注意它和*RPG存档*不是一个东西。不过似乎11的人有意让*RPG积分*替换掉*RPG存档*，也就是开启了*RPG积分*就会让*RPG存档*失效。(这点我没有证实过，存疑)
*RPG存档*相比，*RPG积分*也能提供类似存档的功能，同时提高了存储的容量(据说没有上限，不过你疯狂使用的话，说不定11就会做限制了)、也加入了校验机制防止作弊。

## 权限获取

找11平台的人申请。

## 配置积分

进入11的[RPG地图作者后台](http://rpg.5211game.com/)，应该能看到你在11上架的图。如果看不到，参考上一条。

右上角找到*编辑积分*，里面有8项，这里的意思实际就是在11平台里显示的8项数据，和*RPG存档*的标题是一个意思。只是现在需要在后台编辑，地图里就不会写了。左边是积分的标题，类似于助攻、逃跑之类的；右边是要显示的数据的计算公式，实际上就是一段lua代码，这个代码怎么写我们稍后再讨论。

配置好后，你可以上传一张地图用于测试，点右上角的*添加地图版本+*，按它的提示操作就好了。上传好后，记得把地图的积分开关打开。

静待10~20分钟后，在11平台的RPG专区的内网里找到一个叫*RPG作者自测房*，你刚才上传的地图应该已经在上面了，好好测试下吧。什么，你问我怎么进内网？我也不知道，请参考第一条。

测试无误的话，回到刚才的[RPG地图作者后台](http://rpg.5211game.com/)，申请上架，就算大功告成了。（当然也可能依然是拿你的地图在扣扣里塞给11的人，这个我也不清楚）

## 积分制作

首先你得有最新的YDWE(1.30+)，在*存档[YDWE]*分类里，以*RPG积分*开头就是了。然后其实和*RPG存档*没啥区别，不过多了一个*累加型*和*覆盖型*的概念，所以这里简单介绍下。

覆盖型就和*RPG存档*是一样的，如果你比较懒/比较蠢/觉得无所谓/嫌麻烦全用覆盖型也是可以的。累加型是*RPG积分*新加的概念，它其实就是人为地加上一些限制，以防止作弊行为。再次强调下和覆盖型相比累加型的优点是防作弊更好，缺点是麻烦、不灵活。

其实UI里的注释把用法都说得很清楚了，这里就不说了吧。

## 平台积分的显示

最复杂的留到最后，这个就是第二条里那个*编辑积分*的配置。编辑好后，同样是静待10~20分钟后，去平台里看结果。由于测试一次麻烦，所以我说的很多也只是我猜测的，不一定很对，还是得靠大家摸索吧，或者参考第一条。

所有的代码之前记得有*return*。(所以为什么得有*return*呢)

1. 最简单的例子，效果是永远显示0

```lua
return 0
```

2. 显示指定的值，效果是显示你积分里被你设置为*akari*的值

```lua
return akari
```

3. 中文的积分项，不要问我为什么要这么写

```lua
return _ENV['阿卡林']
```

4. 运算也是可以的

```lua
return _ENV['胜利'] / _ENV['局数']
```

5. 其他lua语法大概也行，比如

```lua
return ((function ()
local r = _ENV['胜利'] / _ENV['局数']
if r < 0.3 then
return '萌新'
elseif r < 0.6 then
return '凡人'
else
return '触手'
end
end))()
```
