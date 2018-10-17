## API OF INTEGRATION

- [API 对接文档协议](#api-%E5%AF%B9%E6%8E%A5%E6%96%87%E6%A1%A3%E5%8D%8F%E8%AE%AE)
- [文档说明](#%E6%96%87%E6%A1%A3%E8%AF%B4%E6%98%8E)
- [文档更新记录](#%E6%96%87%E6%A1%A3%E6%9B%B4%E6%96%B0%E8%AE%B0%E5%BD%95)
- [接入准备](#%E6%8E%A5%E5%85%A5%E5%87%86%E5%A4%87)
- [广告获取流程](#%E5%B9%BF%E5%91%8A%E8%8E%B7%E5%8F%96%E6%B5%81%E7%A8%8B)
- [接入说明](#%E6%8E%A5%E5%85%A5%E8%AF%B4%E6%98%8E)
    - [请求 URL](#%E8%AF%B7%E6%B1%82-url)
    - [通信方式及编码](#%E9%80%9A%E4%BF%A1%E6%96%B9%E5%BC%8F%E5%8F%8A%E7%BC%96%E7%A0%81)
    - [请求头](#%E8%AF%B7%E6%B1%82%E5%A4%B4)
    - [Request 信息](#request-%E4%BF%A1%E6%81%AF)
        - [app 对象信息](#app-%E5%AF%B9%E8%B1%A1%E4%BF%A1%E6%81%AF)
        - [Device 对象信息](#device-%E5%AF%B9%E8%B1%A1%E4%BF%A1%E6%81%AF)
            - [Screen 对象信息](#screen-%E5%AF%B9%E8%B1%A1%E4%BF%A1%E6%81%AF)
            - [Geo 对象信息](#geo-%E5%AF%B9%E8%B1%A1%E4%BF%A1%E6%81%AF)
        - [User 对象信息](#user-%E5%AF%B9%E8%B1%A1%E4%BF%A1%E6%81%AF)
        - [Ad 对象信息](#ad-%E5%AF%B9%E8%B1%A1%E4%BF%A1%E6%81%AF)
            - [Native 对象信息](#native-%E5%AF%B9%E8%B1%A1%E4%BF%A1%E6%81%AF)
                - [Asset 对象信息](#asset-%E5%AF%B9%E8%B1%A1%E4%BF%A1%E6%81%AF)
    - [Response 返回信息](#response-%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AF)
        - [Ad 对象信息](#ad-%E5%AF%B9%E8%B1%A1%E4%BF%A1%E6%81%AF)
            - [Native 对象信息](#native-%E5%AF%B9%E8%B1%A1%E4%BF%A1%E6%81%AF)
            - [Asset 对象信息](#asset-%E5%AF%B9%E8%B1%A1%E4%BF%A1%E6%81%AF)
                - [Image 对象信息](#image-%E5%AF%B9%E8%B1%A1%E4%BF%A1%E6%81%AF)
                - [Title 对象信息](#title-%E5%AF%B9%E8%B1%A1%E4%BF%A1%E6%81%AF)
                - [Data 对象信息](#data-%E5%AF%B9%E8%B1%A1%E4%BF%A1%E6%81%AF)
            - [Link 对象信息](#link-%E5%AF%B9%E8%B1%A1%E4%BF%A1%E6%81%AF)
        - [附件](#%E9%99%84%E4%BB%B6)
            - [应用类别](#%E5%BA%94%E7%94%A8%E7%B1%BB%E5%88%AB)

## Introduction of document

This document is only for developers who use the API with ZPLAY Ads.

## Changelog

| Version | Modifier | Time       | Description |
| ---- | ---- | ---------- | ---- |
| v0.1 | niu  | 2018.09.20 | Creat |

## Preparation before integration

Please get 'Account ID' and 'Token' from your account manager.

## Steps of request

1. When the user visit the APP of developer, developer should send a request to ZPLAY Ads.
2. ZPLAY Ads return a response to developer, both request and response should obey the format agreed by this document.
3. Developer renders the ads according specification of this document

## Instruction

### Request URL

When you send a request, send a HTTP POST to the following address: pa-engine.zplayads.com/v1/api/ads

### Communication Mode and Encoding

Communication protocal: HTTP
Method: POST
Data format: UTF-8

### Request Header

| http header information  | instrction                                                                                                                                                                                                              |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| X-Forwarded-For | Include the real request address of the client, e.g. “8.8.8.8”. If integrated via server, please pass client address because server address will be blocked and regarded as fraud.                                                                             |
| User-Agent      | User Agent of mobile device，e.g. “Mozilla/5.0 (iPad; CPU OS 5_0 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9A334 Safari/7534.48.3”. Non-real User-Agent from server will be regarded as problematic traffic. |

### Request 

| Parameter   | Type        | Mendatory | Description                                                                                                                                 |
| ---------- | ----------- | ---- | ------------------------------------------------------------------------------------------------------------------------------------ |
| ver        | string      | Y   | Protocal version,                                                                                                              |
| developer_token  | string      | Y   | Developer token, offered by ZPLAY Ads account nameger                                                                                          |
| need_https | int         | N   | For material's link or tracking url link, whether the prefix is https. 0 as default. 0: don’t need https, 1: need https for all materials and links. |
| app        | object        | Y   | APP information                                                                                                                         |
| device     | object        | Y   | 设备信息                                                                                                                             |
| user       | object        | N   | 用户信息                                                                                                                             |
| ads        | ad rray of object | YES   | 广告信息数组                                                                                                                         |

#### app 对象信息

| 字段类型 | 类型   | 必须 | 描述                                                                                                                                 |
| -------- | ------ | ---- | ------------------------------------------------------------------------------------------------------------------------------------ |
| app_id   | string | 是   | 应用 ID，请提前将您的应用注册到 ZPLAY Ads 平台 [https://www.zplayads.com](https://www.zplayads.com)，该 ID 为注册后平台生成的应用 ID |
| app_name     | string | 是   | 应用名称                                                                                                                             |
| bundle_id   | string | 是   | 对于 Android，是应用的 packageName；对于 iOS，是 iTunes ID                                                                                                               |
| version      | string | 是   | 应用版本号                                                                                                                           |
| cat      | string | 否   | 应用类别，如“Action”，内容详见[应用类别](#应用类别)                                                                                  |

#### Device 对象信息

| 字段名称        | 类型    | 必须 | 描述                                                                  |
| --------------- | ------- | ---- | --------------------------------------------------------------------- |
| model           | string  | 是   | 设备型号                                                              |
| manufacturer    | string  | 否   | 生产厂商，例如：“Samsung”                                             |
| brand           | string  | 否   | 手机品牌，例如：“MI4”                                                 |
| plmn            | string  | 是   | 国家运营商编号                                                        |
| device_type     | string  | 是   | 设备类型，“phone”，“tablet”                                           |
| adt             | boolean | 否   | 是否允许通过追踪用户行为进行定向投放，0：不允许，1：允许，默认为 1    |
| connection_type | string  | 是   | 网络类型，空串表示未知，值为 wifi，2g，3g，4g，ethernet，cell_unknown |
| carrier         | int     | 是   | 运营商，0：移动，1：电信，3：联通，4：unknown                         |
| orientation     | int     | 否   | 设备方向，“0”为横屏，“1”为竖屏                                        |
| mac             | string  | 否   | MAC 地址, md5 散列                                                    |
| imei            | string  | 否   | IMEI 码，md5 散列。iOS 没有                                           |
| imsi            | string  | 否   | imsi，md5 散列                                                        |
| android_id      | string  | 否   | Android Device ID，md5 散列。Android 手机不传会影响填充               |
| android_adid    | string  | 否   | Android Advertising ID                                                |
| idfa            | string  | 是   | iOS 系统的 idfa。                                                     |
| idfv            | string  | 否   | idfv                                                                  |
| openudid        | string  | 否   | openudid                                                              |
| local           | string  | 否   | 设备上的本地首选项设置                                                |
| language        | string  | 是   | 系统语言                                                              |
| os_type         | string  | 是   | 操作系统类型，值为"iOS"， "Android"， "WP"(windows phone)             |
| os_version      | string  | 是   | 操作系统版本，值为 11.4.1，12.0，7.1.0                                |
| screen          | 对象    | 是   | 设备的屏幕信息                                                        |
| geo             | 对象    | 否   | 设备的位置信息                                                        |

##### Screen 对象信息

| 字段名称 | 类型  | 必须 | 描述                                                                    |
| -------- | ----- | ---- | ----------------------------------------------------------------------- |
| width        | int   | 是   | 水平分辨率，单位：像素                                                  |
| height        | int   | 是   | 纵向分辨率，单位：像素                                                  |
| dpi      | int   | 是   | 像素密度，单位：每英寸像素个数                                          |
| pxratio  | float | 否   | 屏幕物理像素密度，例：iPhone 3 为 1，iPhone 4 为 2，iPhone 6S plus 为 3 |

##### Geo 对象信息

| 字段名称        | 类型   | 必须 | 描述                   |
| --------------- | ------ | ---- | ---------------------- |
| lat             | double | 是   | 纬度                   |
| lon             | double | 是   | 经度                   |
| horizontal_accu | int    | 否   | 水平方向精度，单位：米 |
| vertical_accu   | int    | 否   | 垂直方向精度，单位：米 |

#### User 对象信息

| 字段名称 | 类别   | 必须 | 描述                                 |
| -------- | ------ | ---- | ------------------------------------ |
| id       | string | 否   | 用户 id                              |
| gender   | int    | 否   | 性别，0：女，1：男，2：其他，3：未知 |
| age      | int    | 否   | 年龄                                 |
| keywords | array  | 否   | 用户感兴趣的关键词                   |

#### Ad 对象信息

| 字段名称   | 类别   | 必须 | 描述                                                                                                                              |
| ---------- | ------ | ---- | --------------------------------------------------------------------------------------------------------------------------------- |
| unit_type  | int    | 是   | 广告位类型，0：横幅，1：插屏，2：开屏，3：原生，4：视频，当前仅支持插屏，原生和视频三种类型，类型需与您广告位 ID 类型保持一致     |
| ad_unit_id | string | 否   | 广告位 id，请提前将您的广告位注册到 ZPLAY Ads 平台 [https://www.zplayads.com](https://www.zplayads.com) ，该 ID 为注册后生成的 ID |
| native     | 对象   | 否   | 原生广告位信息                                                                                                                    |

##### Native 对象信息

| 字段名称 | 类型       | 必须 | 描述                                                                                                                   |
| -------- | ---------- | ---- | ---------------------------------------------------------------------------------------------------------------------- |
| layout   | int        | 是   | 原生广告类型，1： 内容墙， 2： 应用墙，3：新闻流， 4：聊天列表，5：走马灯广告，6：内容流，7：矩阵                      |
| assets   | Asset 数组 | 是   | 原生广告元素列表，当前有 5 种元素，分别为标题 (title)， Icon(img)， Large image (img)，Description (data)，得分 (data) |

###### Asset 对象信息

| 字段名称 | 类型 | 必须 | 描述                                         |
| -------- | ---- | ---- | -------------------------------------------- |
| id       | int  | 是   | 广告元素 id                                  |
| required | int  | 否   | 广告元素是否必须，1：必须，0：可选，默认为 0 |
| title    | 对象 | 否   | 文字元素                                     |
| image      | 对象 | 否   | 图像元素                                     |
| data     | 对象 | 否   | 其他数据元素                                 |

> image，title，data 这三个元素，一个 asset 只能存在一个

**Image 对象信息**

| 字段名称 | 类型 | 必须 | 描述                                                                                                                                                               |
| -------- | ---- | ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| type     | int  | 是   | image 元素的类型，1：图标，2：品牌 Logo，3：大图，4：“免安装试玩”按钮，当用户点击“免安装试玩”按钮时，请将response.ads中的 playable_ads_html 加载到 webview 中 |
| width        | int  | 是   | image 元素的宽度，单位为像素                                                                                                                                       |
| height        | int  | 是   | image 元素的高度，单位为像素                                                                                                                                       |

**Title 对象信息**

| 字段名称 | 类型 | 必须 | 描述                   |
| -------- | ---- | ---- | ---------------------- |
| len      | int  | 是   | title 元素最大文字长度 |

**Data 对象信息**

| 字段名称 | 类型 | 必须 | 描述                                                                                                                                                                                                                                        |
| -------- | ---- | ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type     | int  | 是   | 数据类型 1：Sponsor 名称，应该包含品牌名称，2：描述，3：打分，4：点赞个数，5：下载个数，6： 产品价格，7：销售价格，往往和前者结合，表示折扣价，8：电话，9：地址，10：描述 2，11：显示的链接，12：行动按钮名称，1001：视频 url，1002：评论数 |
| len      | int  | 是   | 元素最大文字长度                                                                                                                                                                                                                            |

### Response 返回信息

| 字段名称 | 类型        | 必须 | 描述                                                           |
| -------- | ----------- | ---- | -------------------------------------------------------------- |
| result   | int         | 是   | 返回结果，0：成功，小于 0 表示失败                             |
| msg      | string      | 否   | 失败的话，会填写失败原因，例："网络错误"，在这里列出具体的原因 |
| ads      | ad 对象数组 | 否   | 如果失败，或者无对应广告则无此数据                             |
| cur      | string      | 否   | 广告价格货币类型，默认为"CNY"                                  |

#### Ad 对象信息

| 字段名称          | 类型   | 必须 | 描述                                                                                                                      |
| ----------------- | ------ | ---- | ------------------------------------------------------------------------------------------------------------------------- |
| id                | string | 是   | 广告 id                                                                                                                   |
| ad_unit_id        | string | 是   | 广告位 id，与 request 中的 ad_unit_id 对应                                                                                |
| app_bundle        | string | 是   | 对于 Android，是应用的 packageName；对于 iOS，是 iTunes ID ，请监听可玩广告的 `user_did_tap_install` 事件，在监听到时在 APP 内部打开 APP Store 或者 Google Play，并打开跳转链接                                                       |
| playable_ads_html | string | 是   | 可玩广告的 html 代码，请确保使用应用内的 webview 中打开                                                                   |
| target_url               | string | 是   | 可玩广告的跳转地址 |
| target_url_type         | int    | 是   | 打开可玩广告跳转地址时的打开方式，1：在 app 内 webview 打开目标链接，2：在系统浏览器打开目标链接，3：打开地图，4：拨打电话，5：播放视频，6：App 下载，请确保在应用内打开 APP Store 或者 Google Play |
| price             | float  | 否   | 广告价格，若没有该数据则为 0，单位为分                                                                                    |
| native            | 对象   | 否   | 原生广告对象，如果广告位类型是原生时，返回此对象                                                                          |

##### Native 对象信息

| 字段名称   | 类型           | 必须 | 描述                                                                                                           |
| ---------- | -------------- | ---- | -------------------------------------------------------------------------------------------------------------- |
| assets     | Asset 对象数组 | 是   | 原生广告元素列表，当前主要支持 4 种元素，分别为标题 (title)， 图标(img)， 大图(img)， 描述 (data)，得分 (data) |
| imp_tracker | 数组           | 否   | 展示跟踪地址数组，需要返回一个 1x1 像素图片                                                                    |
| link       | 对象           | 是   | 原生广告的目标链接，默认链接对象，当 assets 中不包括 link 对象时，使用此对象                                   |

##### Asset 对象信息

| 字段名称 | 类型 | 必须 | 描述                                              |
| -------- | ---- | ---- | ------------------------------------------------- |
| id       | int  | 是   | 广告元素 ID                                       |
| required | int  | 否   | 广告元素是否必须显示，1：必须，0：可选， 默认为 0 |
| title    | 对象 | 否   | 文字元素                                          |
| image      | 对象 | 否   | 图像元素                                          |
| data     | 对象 | 否   | 其他数据元素                                      |
| link     | 对象 | 否   | 点击目标链接                                      |

###### Image 对象信息

| 字段名称 | 类型   | 必须 | 描述                         |
| -------- | ------ | ---- | ---------------------------- |
| url      | string | 是   | image url 地址               |
| width    | int    | 否   | image 元素的宽度，单位为像素 |
| height   | int    | 否   | image 元素的宽度，单位为像素 |

###### Title 对象信息

| 字段名称 | 类型   | 必须 | 描述     |
| -------- | ------ | ---- | -------- |
| text     | string | 是   | 标题文字 |

###### Data 对象信息

| 字段名称 | 类型   | 必须 | 描述     |
| -------- | ------ | ---- | -------- |
| label    | string | 否   | 数据名称 |
| value    | string | 是   | 数据正文 |

##### Link 对象信息

| 字段名称     | 类型   | 必须 | 描述                                                                                                                                                                            |
| ------------ | ------ | ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| target_url          | string | 是   | 目标链接，优先使用外层的app_bundle字段跳转                                                                                                                                                                        |
| app_bundle        | string | 是   | 对于 Android，是应用的 packageName；对于 iOS，是 iTunes ID ，请监听可玩广告的 `user_did_tap_install` 事件，在监听到时在 APP 内部打开 APP Store 或者 Google Play，并打开跳转链接                                                       |
| click_tracker | 数组   | 否   | 点击追踪链接                                                                                                                                                                    |
| target_url_type         | int    | 是   | 打开可玩广告跳转地址时的打开方式，1：在 app 内 webview 打开目标链接，2：在系统浏览器打开目标链接，3：打开地图，4：拨打电话，5：播放视频，6：App 下载，请确保在应用内打开 APP Store 或者 Google Play |

#### 附件

##### 应用类别

| ID                                   | 应用类别     | Category      |
| ------------------------------------ | ------------ | ------------- |
| AD9C1D4C-272D-7E6B-BB64-B770A8A5B9B0 | 动作游戏     | Action        |
| AED099F1-2B7E-9A52-9F2E-D4F7CFE500AA | 益智解谜     | Puzzle        |
| 7AD7776C-20D1-7A2A-9388-0D67A44FF399 | 卡牌游戏     | Card          |
| 36FBA1A1-C5E7-D9F6-9170-9BA0DA13CBF9 | 休闲         | Casual        |
| 1CF3914A-E099-92A5-0ECF-D3C05A177253 | 冒险游戏     | Adventure     |
| 40E3C001-ADF6-A950-6E73-5DB66B0648E3 | 角色扮演游戏 | Role-playing  |
| 7DA00174-66E2-5119-6355-331049316283 | 策略游戏     | Strategy game |
| F3C58318-6A2E-223E-C3D5-5936C48196B1 | 街机游戏     | Arcade        |
| AEDADC6C-562B-751F-E137-907A605BAA6C | 儿童         | Kids          |
| 34879F45-896A-FFA9-582E-D576345F1D9A | 竞速游戏     | Racing        |
| C91C130E-3166-FB45-8951-25DC86850C12 | 聚会游戏     | Family        |
| E13A497E-BCFA-1E66-05E4-31B716765B5B | 模拟游戏     | Simulation    |
| CEDC63B5-9A57-DFD0-75CB-1289DEB7578A | 体育         | Sports        |
| 48EF79CA-B384-F7A8-736A-423E8D62A023 | 文字游戏     | Word          |
| 7F43E937-69EA-5C4A-954B-E52B10094225 | 问答游戏     | Trivia        |
| 59B07A55-A40B-0D29-BF2D-CF29AFED540E | 音乐         | Music         |
| EC5336A4-A434-BDDA-4246-6F50DA2EF63E | 桌面游戏     | Board         |
| 57728DCB-9EC5-DC08-B999-3F9DDDF66083 | 赌场         | Casino        |
| CB45DD59-EF28-EC0D-423B-2ED10F54C8D7 | 教育         | Education     |