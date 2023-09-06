# 自动翻译使用说明

> composer require luguohuakai/fanyi:~1.0.0
>
> php >= 7.4

* 首次使用请自行到百度翻译申请APP_ID/APP_SECRET; 并写入./fanyi.ini;
* 注意不要把自己的APP_ID/APP_SECRET提交到git, 用多了是要收费的
* 申请地址: https://fanyi-api.baidu.com/api/trans/product/desktop

* 使用方式: `php ./vendor/luguohuakai/fanyi/fanyi --file=./center/messages/en/app.php --language=en`

* 参数解释: `--file=./en/app.php` : 需要翻译的翻译文件; 如: `./zh-CN/log.php`
* 参数解释: `--language=en` : 需要翻译成什么语言; 见下面`常见语种列表`
* 注意: 参数位置和格式是固定的不要变动
* 注意: 翻译完成后需要亲自检查一下, 看看对不对, 不对的地方手动调整一下

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

> 更多语言支持请查看: https://fanyi-api.baidu.com/doc/21