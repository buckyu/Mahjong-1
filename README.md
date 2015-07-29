# Mahjong

本项目为一个麻将服务器，供AI比赛使用。本文档分为两部分，第一部分为此服务器使用的麻将规则，第二部分为交互的接口规范。

## 规则

为降低复杂度，本规则以国标麻将为基础进行了大量的简化。

### 注意点

* 麻将牌共136张，即在国标麻将的基础上去掉了八张花牌。
* 去除圈、局的概念，盘数定为100盘。同时也去除了圈风、门风、庄家的概念。
* 去除轮转，四位AI的位置会在整场比赛开始的时候由服务器随机确定。
* 没有牌城、掷骰与开牌的概念，AI拿到的牌全部直接由服务器发放。
* 整场比赛的第一盘时，第一个行牌的AI由服务器随机决定，从第二盘开始第一个行牌的AI为最近和牌的AI。
* 没有起和番数

### 番种

国标麻将的番种非常多，本规则将番种大大精简。

##### 88番

* 大四喜
* 大三元
* 十三幺
* 绿一色
* 四杠

##### 64番

* 小四喜
* 小三元
* 字一色
* 四暗刻
* 清幺九

##### 32番

* 三杠
* 混幺九

##### 24番

* 七对
* 清一色

##### 16番

* 三同刻
* 三暗刻

##### 8番

* 三色三同顺

##### 6番

* 碰碰和
* 混一色
* 五门齐

##### 2番

* 门前清
* 断幺
* 平和
* 箭刻
* 暗杠

##### 1番

* 自摸
* 无字
* 一般高
* 喜相逢
* 幺九刻
* 明杠
* 单钓将

### 记分规则

最开始每位AI的分数都是0分。底分为1分，基本分和牌后各个番种分数的总和。

若和牌方自摸，则另外三家都需付给和牌方（底分＋基本分）的分数。

否则，点炮方付给和牌方（底分＋基本分）的分数，其余两家付给和牌方基本分的分数。

