# ð¤ kiwi linter
> æ¬æä»¶ fork äº[é¿éå·´å·´çå®æ¹ä»åº](https://github.com/zhuqingguang/kiwi)ï¼å¨å¶åºç¡ä¸è¿è¡ä¼åä¸æ©å±ï¼æ¯ææ´çµæ´»çä½¿ç¨æ¹å¼ãæè°¢é¿éå·´å·´åå­¦çå·¥ä½ï¼å¦ææ¬ä»åºä¾µç¯äºæ¨çæå©ï¼å¯ä»¥èç³»æ~


kiwi ç `VS Code`æä»¶å·¥å·ï¼ä¸»è¦ç¨äºæ£æµä»£ç ä¸­çä¸­æï¼é«äº®åºä¸­æå­ç¬¦ä¸²ï¼å¹¶ä¸é®æåä¸­æå­ç¬¦ä¸²å°å¯¹åºçè¯­è¨ Key åºã

åæ¶ä¼åå¼åä½éªï¼å¨ `VS Code` ä¸­æä¾æç´¢ä¸­æï¼æç¤ºå½éåå¼å¯¹åºçä¸­æåè½ã

## å¦ä½ä½¿ç¨

> VS Code æä»¶æç´¢ better-i18n-linter å®è£

> æ¨èä¸[ð¤ Kiwi-å½éåå¨æµç¨è§£å³æ¹æ¡](https://github.com/alibaba/kiwi)ç»åä½¿ç¨


![æ¼ç¤º](https://img.alicdn.com/tfs/TB1EYENfTnI8KJjy0FfXXcdoVXa-1006-368.gif)

![å±ç¤º](https://img.alicdn.com/tfs/TB1pzAIC4YaK1RjSZFnXXa80pXa-884-308.png)

## éç½®é¡¹

### better-i18n-linter.langPrefix

default: `src/lang/zh-CN/`

å¤è¯­è¨æä»¶çä½ç½®, kiwi linterå°æ ¹æ®ç®å½åçå¤è¯­è¨æä»¶æåå¯¹åºè¯­è¨(é»è®¤ä¸ºä¸­æ`zh-CN`)é«äº®.
å¯ä»¥åèçç®å½ç»æå¦ä¸:
![ç¤ºä¾ç®å½ç»æ](./assets/i18n-folder-structure.gif)

### better-i18n-linter.i18nFilesPattern

default: `**/src/**/*.+(vue|js*|html|ts*)`

å¾æ«æçæä»¶ç±»åï¼å¯ä»¥åºäº [minimatch](https://github.com/isaacs/minimatch) è§åè¿è¡èªå®ä¹ã

## å¤å·¥ç¨æ¯æ
> è¿ä¸ªæ¯åæçåè½ï¼ä¸è¿éç¨äºéç½®æä»¶çæ¹å¼èä¸æ¯ VS Code éç½®çæ¹å¼è¿è¡éç½®ã
æ¯æå¤ä¸ªæä»¶å¤¹ä½¿ç¨åèªä¸åçè¯­è¨åéç½®ï¼åªéå¨é¡¹ç®æ ¹ç®å½ä¸åå»º `.kiwi` æä»¶ï¼åå¥éç½®å³å¯ï¼
```json
{
    "kiwiDir": [
      "src/common/i18n"
    ],
    "importStatement": "import { I18N } from '@/common/i18n';",
    "i18nFilesPattern": "src/pages/**/*.{js,vue,ts,tsx}",
    // mono-repo å·¥ç¨ä½¿ç¨
    "projects": [
        {
            "target": "packages/package-a",
            "kiwiDir": [
                "packages/common/src/lang",
                "packages/package-a/src/lang"
            ]
        }
    ]
}
```
- `markStringLiterals`, default: `true`, æ¯å¦æ çº¢ä¸­æå­ç¬¦ä¸²ï¼é»è®¤å¼å¯ã
- `showOverviewRuler`: default: `true`,å³ä¾§æ»å¨æ¡ä¸­ï¼æ¯å¦æ¾ç¤ºå¯¹åºçå¾æå ![ä¸­æé«äº®](https://img.alicdn.com/tfs/TB1CHZRrxGYBuNjy0FnXXX5lpXa-1088-568.png)
- `markColor`: string, default: `#ff4400`, å¾æåæå­ï¼é«äº®é¢è²
- `kiwiDir`: string[], å½åææå¤è¯­è¨æä»¶æå¨çç®å½ï¼ä¾å¦ææå¤è¯­è¨æä»¶å­æ¾å¨ `src/common/i18n` ä¸ï¼å³å¯è®¾ç½® `[src/common/i18n]`
- `i18nFilesPattern`: string, è®¾ç½®éè¦æ£æµæ±å­çæä»¶ï¼æ¯æ glob è¯­å¥,å¦ `src/pages/**/*.{js,vue,ts,tsx}`
- `importStatement`: string, å½å¨æ²¡æå¯¼å¥è¿ `I18N` çæä»¶ä¸­èªå¨æåä¸­ææ¶ï¼ä¼èªå¨æå¥å¯¼å¥çè¯­å¥ã
- `projects.target`: string, ç®æ æä»¶æå¨ç**ç¸å¯¹**ç®å½åç¼ï¼åé¨ä½¿ç¨ `fileUri.indexOf(target)` çæ¹å¼å¤æ­æ¯å¦åºç¨è¯¥å·¥ç¨éç½®ï¼
- `projects.kiwiDir`: string | string[], ä¸­æåæå¨çç®æ ç®å½ï¼å¯ä»¥éç½®ä¸ä¸ªæå¤ä¸ªï¼
- `projects.importStatement`: string, æ¬å·¥ç¨å¯¹åºçèªå¨å¯¼å¥çè¯­å¥ï¼

> éç½®ä¸­çææè·¯å¾åä¸ºç¸å¯¹äºå·¥ç¨çç¸å¯¹è·¯å¾ã

## VS code å½ä»¤

### å¨å¨é¨ä»£ç åºä¸­æ¥æ¾å½éåææ¡
é»è®¤å¿«æ·é®æ¯ `cmd + ctrl + r`.


### å¨å½åæä»¶ä¸­æ¥æ¾å½éåææ¡
é»è®¤å¿«æ·é®æ¯ `cmd + ctrl + f`.

![](https://img.alicdn.com/tfs/TB1dzf8rpOWBuNjy0FiXXXFxVXa-1256-700.png)

