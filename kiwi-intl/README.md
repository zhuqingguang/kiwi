# ð¤ kiwi-intl [![npm version](https://badge.fury.io/js/kiwi-intl.svg)](http://badge.fury.io/js/kiwi-intl)

éç¨çå½éåæ¡æ¶ï¼ä¸ç»å®ä»»ä½æ¡æ¶ã

## å¦ä½ä½¿ç¨

> yarn add kiwi-intl

> æ¨èä¸[ð¤ Kiwi-å½éåå¨æµç¨è§£å³æ¹æ¡](https://github.com/zhuqingguang/kiwi)ç»åä½¿ç¨

## ä½¿ç¨ API

åå§åå½éåæ¡æ¶

```javascript
import KiwiIntl from 'kiwi-intl';

const kiwiIntl = KiwiIntl.init('en-UK', {
  'en-UK': {
    test: 'testvalue',
    testTemplate: 'you have {value} unread message',
    photo:
      'You have {num, plural, =0 {no photos.} =1 {one photo.} other {# photos.}}'
  },
  'zh-CN': {
    lang: 'è¯­è¨'
  }
});
```

å¨ç»ä»¶ä¸­ç´æ¥ä½¿ç¨ï¼æ¯ææ¨¡æ¿, åå¤æ°ãåæ¶æ¯æ `kiwiIntl.test`,ç´æ¥åå¯¹åº Key å¼ã

```javascript

kiwiIntl.test; // testvalue;

kiwiIntl.get('test'); // testvalue;

kiwiIntl.get('testTemplate', {
  value: three
}); // å¼æ¯ 'you have three unread message'

kiwiIntl.template(kiwiIntl.testTemplate, {
  value: three
}); // å¼æ¯ 'you have three unread message'

kiwiIntl.get('photo', {
  num: 0
}); // å¼æ¯ 'You have no photos.'
```

åæ¢è¯­è¨

```javascript
kiwiIntl.setLang('zh-CN'); // åæ¢å°ä¸­æè¯­è¨
```
## è¯­è¨ç¼ç 
ãå¼ºå¶ãåºå«ä¸åè¯­è¨ç language tag éµå¾ª [BCP47](https://en.wikipedia.org/wiki/IETF_language_tag) è§èã

æ ¹æ®ç®åçå½éä¸å¡æåµï¼ä¸åå°åºçåç§è¯­è¨å¨åä¸å°åºä¸ä¼åä½¿ç¨ä¸¤ç§åæ³ãæ¯å¦æ°å å¡åªä½¿ç¨æ¯ç®ä½ä¸­æï¼å°æ¹¾åé¦æ¸¯åªä½¿ç¨ç¹ä½ä¸­æï¼æä»¥æä»¬çº¦å®å¨ BCP 47è§èä¸­ï¼ä»ä½¿ç¨ language-region  çç»åæ¹å¼ã

æ­£ä¾ï¼zh-CN

åä¾ï¼~~zhãzh_hansãzh-cn~~



## License

MIT
