# 自动翻译使用说明

* 主要用于翻译Yii2的php翻译文件, php文件内返回的是一个数组, 或者类似以下这种都可以翻译
* 注意: `=>` 这个符号两边有且只能有一个空格; 只会翻译值为空字符串的项

```php
<?php
// 测试文件
return [
    'Operator' => '',
    'What are you doing' => '你在干什么',
    'Ok ok' => '好的好的',
    '可以的' => '',
    'What' => '什么',
    'haha' => '哈哈',
    'abc' => '',
    'Delete' => '删去',
    'Update' => '',
];
```

> composer require luguohuakai/fanyi:~1.0.3 --dev
>
> php >= 7.4

* 首次使用请自行到百度翻译申请APP_ID/APP_SECRET; 并写入./fanyi.ini;
* 注意不要把自己的APP_ID/APP_SECRET提交到git, 用多了是要收费的
* 申请地址: https://fanyi-api.baidu.com/api/trans/product/desktop

* 使用方式: `php ./vendor/bin/fanyi --file=./center/messages/en/app.php --language=en`

* 参数解释: `--file=./en/app.php` : 需要翻译的文件位置; 如: `./zh-CN/log.php`
* 参数解释: `--language=en` : 需要翻译成什么语言; 见下面`常见语种列表`
* 注意: 参数位置和格式是固定的不要变动
* 注意: 翻译完成后需要亲自检查一下, 看看对不对, 不对的地方手动调整一下

## 高级功能

* `php ./vendor/bin/fanyi --file=./center/messages/en/app.php --language=en --match=/^\d+/ --base=./center/messages/zh-CN/app.php`
* 如果匹配规则成立则去基准文件找对应value值进行翻译
* 参数解释: `--match=/^\d+/`: 正则匹配; 常用: /^\d+/(由多个数字组成), /^T\d+/(如: T10003 E7001); 如有多个用英文逗号隔开 如: `--match=/^\d+/,/^T\d+/`
* 参数解释: `--base=./center/messages/zh-CN/app.php`: 基准文件, 会去找这个文件中key对应的value进行翻译
* 注意: 参数位置和格式是固定的不要变动
* 特殊参数: `--mathc=all`: 代表全部从基准文件找

## 常见语种列表

| 名称     | 代码   | 名称    | 代码  | 名称    | 代码  |
|--------|------|-------|-----|-------|-----|
| 自动检测   | auto | 中文    | zh  | 英语    | en  |
| 粤语     | yue  | 文言文   | wyw | 日语    | jp  |
| 韩语     | kor  | 法语    | fra | 西班牙语  | spa |
| 泰语     | th   | 阿拉伯语  | ara | 俄语    | ru  |
| 葡萄牙语   | pt   | 德语    | de  | 意大利语  | it  |
| 希腊语    | el   | 荷兰语   | nl  | 波兰语   | pl  |
| 保加利亚语  | bul  | 爱沙尼亚语 | est | 丹麦语   | dan |
| 芬兰语    | fin  | 捷克语   | cs  | 罗马尼亚语 | rom |
| 斯洛文尼亚语 | slo  | 瑞典语   | swe | 匈牙利语  | hu  |
| 繁体中文   | cht  | 越南语   | vie | 	     ||

> 更多语言支持请查看(需要企业认证-可能需要收费): https://fanyi-api.baidu.com/doc/21