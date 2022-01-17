<p align="center">
  <a href="https://github.com/rainerosion/skyBadge/blob/master/LICENSE">
    <img src="https://img.shields.io/github/license/rainerosion/skyBadge" alt="license">
  </a>
  <a href="https://github.com/rainerosion/skyBadge">
    <img src="https://img.shields.io/github/stars/rainerosion/skyBadge" alt="stars">
  </a>
  <a href="https://github.com/rainerosion/skyBadge/releases">
    <img src="https://img.shields.io/github/v/release/rainerosion/skyBadge?include_prereleases" alt="release">
  </a>
</p>
# [auto.js]光遇徽章使用脚本

## 初衷

写本脚本的初衷是为了方便使用徽章，不用携带徽章也能随时使用徽章带来的魔法。

实际上光遇NTAG徽章设计，感应区为徽章背面的小圆点部分，而这部分感应区太小且徽章的针扣也在这一面，手机nfc感应区位置问题导致徽章无法放平使用，也无法从背面扫描徽章，经常导致扫描无反应或者需要将徽章在手机nfc感应区移动很久才有反应。

## 当前功能

- 目前只支持网易官方服

- 录入多个徽章信息

- 选择对应徽章使用

## 使用方法

- 使用NFC Tools Pro(其他软件也可)读取实体徽章的URL

- 打当前脚本录入徽章URL

## 注意事项
- auto.js 版本 4.0.0 Beta 及以上

- 首先你需要有光遇实体徽章

- 使用本脚本后如果使用实体徽章后需要重新录入徽章信息，原有的徽章信息会失效。

- 使用本脚本后也可能造成你的徽章失效，需要在NFC下多刷几次，手机有反应即可，无需打开app

## 相关问题 

> 为什么实体徽章会有几次无法使用？

光遇的NTAG徽章中使用了NFC COUNTER(nfc计数器)，每次徽章在nfc下使用徽章使用次次数加会加1（无论你是否打开光遇）。当你打开光遇app时，徽章使用次数会上传到光遇服务器，下一次使用时候会校验使用次数，小于上一次的使用次数时候会抛出异常（徽章验证错误：CANNOT_UPDATE_NFC_COUNTER）。

举个例子：如果你现在的徽章在光遇使用了10次，此时你将徽章信息录入本脚本，本脚本记录的使用次数也是10次。当你再次使用实体徽章时候此时徽章使用次数为11次。脚本中的使用次数依旧为10，打开光遇后就会报错徽章验证错误。当然如果你使用本脚本时次数为20次（使用次数可以手动修改NTAG中url的最后6位16进制数），而你实体徽章次数为15次，相差了5次，此时你需要使用实体徽章在nfc下刷5次后方可使用。

> 执行脚本打开光遇报错 徽章验证错误：CANNOT_UPDATE_NFC_COUNTER

重新录入最新的徽章信息

> 使用脚本后使用实体徽章报错 徽章验证错误：CANNOT_UPDATE_NFC_COUNTER 

多在NFC下刷几次徽章（无需打开光遇app，手机有反应即可）更新徽章使用次数。


## 渠道服务包名

如果你正在使用渠道服，请修改脚本第15行的`com.netease.sky`为下表各个渠道对应的包名，目前收集到的包名见下表（不全）。

| 包名                     | 渠道名称 |
| ------------------------ | -------- |
| com.netease.sky          | 网易     |
| com.netease.sky.bilibili | 哔哩哔哩 |
| com.netease.sky.aligames | 九游     |
