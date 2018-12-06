# 广告请求和返回示例

- [广告请求和返回示例](#%E5%B9%BF%E5%91%8A%E8%AF%B7%E6%B1%82%E5%92%8C%E8%BF%94%E5%9B%9E%E7%A4%BA%E4%BE%8B)
    - [测试 token 和应用](#%E6%B5%8B%E8%AF%95-token-%E5%92%8C%E5%BA%94%E7%94%A8)
    - [代码示例](#%E4%BB%A3%E7%A0%81%E7%A4%BA%E4%BE%8B)
        - [iOS](#ios)
            - [插屏](#%E6%8F%92%E5%B1%8F)
                - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B)
                - [返回示例](#%E8%BF%94%E5%9B%9E%E7%A4%BA%E4%BE%8B)
            - [原生](#%E5%8E%9F%E7%94%9F)
                - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-1)
                - [返回示例](#%E8%BF%94%E5%9B%9E%E7%A4%BA%E4%BE%8B-1)
            - [激励视频](#%E6%BF%80%E5%8A%B1%E8%A7%86%E9%A2%91)
                - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-2)
                - [返回示例](#%E8%BF%94%E5%9B%9E%E7%A4%BA%E4%BE%8B-2)
        - [Android](#android)
            - [插屏](#%E6%8F%92%E5%B1%8F-1)
                - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-3)
                - [返回示例](#%E8%BF%94%E5%9B%9E%E7%A4%BA%E4%BE%8B-3)
            - [原生](#%E5%8E%9F%E7%94%9F-1)
                - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-4)
                - [返回示例](#%E8%BF%94%E5%9B%9E%E7%A4%BA%E4%BE%8B-4)
            - [激励视频](#%E6%BF%80%E5%8A%B1%E8%A7%86%E9%A2%91-1)
                - [请求示例](#%E8%AF%B7%E6%B1%82%E7%A4%BA%E4%BE%8B-5)
                - [返回示例](#%E8%BF%94%E5%9B%9E%E7%A4%BA%E4%BE%8B-5)

## 测试 token 和应用

> 在对接完成后你可以使用测试 token（D0C85086-DC66-433E-9304-49EAB171D008）及测试应用和广告位获取广告（如下），以测试是否接入成功。

| 操作系统 | 测试应用<br>（app_id）               | 测试广告位<br>（ad_unit_id）         | 广告位类型<br>（unit_type） |
| -------- | ------------------------------------ | ------------------------------------ | --------------------------- |
| iOS      | A650AB0D-7BFC-2A81-3066-D3170947C3DA | 0868EBC0-7768-40CA-4226-F9924221C8EB | 1: 插屏                     |
| iOS      | A650AB0D-7BFC-2A81-3066-D3170947C3DA | 25AED008-6B6F-BADB-F873-AE7CA61DFE98 | 3: 原生                     |
| iOS      | A650AB0D-7BFC-2A81-3066-D3170947C3DA | BAE5DAAC-04A2-2591-D5B0-38FA846E45E7 | 4: 激励视频                 |
| Android  | 5C5419C7-A2DE-88BC-A311-C3E7A646F6AF | 19393189-C4EB-3886-60B9-13B39407064E | 1: 插屏                     |
| Android  | 5C5419C7-A2DE-88BC-A311-C3E7A646F6AF | BB8452AD-06E7-140B-00DC-FD6CB6B40FAA | 3: 原生                     |
| Android  | 5C5419C7-A2DE-88BC-A311-C3E7A646F6AF | 3FBEFA05-3A8B-2122-24C7-A87D0BC9FEEC | 4: 激励视频                 |

## 代码示例

### iOS

#### 插屏

##### 请求示例

```json
{
  "version": "1.0",
  "developer_token": "D0C85086-DC66-433E-9304-49EAB171D008",
  "need_https": 1,
  "app": {
    "app_id": "A650AB0D-7BFC-2A81-3066-D3170947C3DA",
    "app_name": "app_name",
    "bundle_id": "com.playableads.demo",
    "version": "1.0",
    "cat": "cat"
  },
  "device": {
    "model": "iphone",
    "manufacturer": "iphone",
    "brand": "apple",
    "plmn": "46001",
    "device_type": "phone",
    "adt": 1,
    "connection_type": "wifi",
    "carrier": 3,
    "orientation": 0,
    "mac": "",
    "imei": "",
    "android_id": "",
    "android_ad_id": "",
    "idfa": "123456789",
    "idfv": "",
    "openudid": "openudid",
    "language": "zh",
    "os_type": "ios",
    "os_version": "11.4.1",
    "screen": {
      "width": 123,
      "height": 234,
      "dpi": 2,
      "pxratio": 34567
    },
    "geo": {
      "lat": 34.567,
      "lon": 107.67,
      "horizontal_accu": 45,
      "vertical_accu": 56
    }
  },
  "user": {
    "id": "34ddd",
    "gender": 0,
    "age": 34,
    "keywords": ["45", "56", "abd"]
  },
  "ads": [
    {
      "unit_type": 1,
      "ad_unit_id": "0868EBC0-7768-40CA-4226-F9924221C8EB"
    }
  ]
}
```

##### 返回示例

```json
{
  "result": 0,
  "msg": "",
  "ads": [
    {
      "id": "6E4ADB48-6674-B91F-AE85-12E8CD21A847",
      "ad_unit_id": "0868EBC0-7768-40CA-4226-F9924221C8EB",
      "msg": "C0EB1023-8170-E612-5ABA-B437C26CC709",
      "app_bundle": "834878585",
      "target_url": "https://itunes.apple.com/cn/app/id834878585?mt=8",
      "target_url_type": 6,
      "playable_ads_html": "<!DOCTYPE html>\n<html>\n  <head>\n    <meta name=\"viewport\" content=\"user-scalable=no, width=device-width, initial-scale=1, maximum-scale=1\">\n    <title>Atmosplayer</title>\n    <meta charset=\"utf-8\"/>\n    <script>\n      window.gestures = [\n  [\n    {\n      \"id\": 0,\n      \"type\": \"tap\",\n      \"attack\": 0,\n      \"target\": 1999,\n      \"fullscreen\": true,\n      \"shapes\": [\n        {\n          \"type\": \"circle\",\n          \"x\": 0.42328042328042326,\n          \"y\": 0.23809523809523808,\n          \"radius\": 0.08465608465608465\n        }\n      ],\n      \"mandatory\": false,\n      \"tapDirection\": 1,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 1,\n      \"type\": \"tap\",\n      \"attack\": 3269,\n      \"loopStart\": 4368,\n      \"target\": 6519,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.5544973544973544,\n          \"y\": 0.5595238095238095,\n          \"width\": 0.33015873015873015,\n          \"height\": 0.15\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 2,\n      \"type\": \"tap\",\n      \"attack\": 7458,\n      \"loopStart\": 8355,\n      \"target\": 10357,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.6476190476190475,\n          \"y\": 0.5952380952380952,\n          \"width\": 0.3386243386243386,\n          \"height\": 0.20714285714285716\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 3,\n      \"type\": \"tap\",\n      \"attack\": 11913,\n      \"loopStart\": 12863,\n      \"target\": 14913,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.45291005291005293,\n          \"y\": 0.5880952380952381,\n          \"width\": 0.182010582010582,\n          \"height\": 0.20952380952380953\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 4,\n      \"type\": \"tap\",\n      \"attack\": 15849,\n      \"loopStart\": 16643,\n      \"target\": 18849,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.30052910052910053,\n          \"y\": 0.5904761904761905,\n          \"width\": 0.2455026455026455,\n          \"height\": 0.19047619047619047\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 5,\n      \"type\": \"tap\",\n      \"attack\": 19786,\n      \"loopStart\": 20736,\n      \"target\": 22736,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.35555555555555557,\n          \"y\": 0.5952380952380952,\n          \"width\": 0.16507936507936508,\n          \"height\": 0.20952380952380953\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 6,\n      \"type\": \"tap\",\n      \"attack\": 23722,\n      \"loopStart\": 24472,\n      \"target\": 26572,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.09312169312169312,\n          \"y\": 0.4976190476190476,\n          \"width\": 0.30052910052910053,\n          \"height\": 0.14523809523809525\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 7,\n      \"type\": \"tap\",\n      \"attack\": 27348,\n      \"loopStart\": 28448,\n      \"target\": 30398,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.10158730158730159,\n          \"y\": 0.530952380952381,\n          \"width\": 0.31322751322751324,\n          \"height\": 0.1\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 8,\n      \"type\": \"tap\",\n      \"attack\": 31284,\n      \"loopStart\": 32134,\n      \"target\": 34129,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.15661375661375662,\n          \"y\": 0.6238095238095238,\n          \"width\": 0.1693121693121693,\n          \"height\": 0.16666666666666666\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 9,\n      \"type\": \"tap\",\n      \"attack\": 34776,\n      \"loopStart\": 35676,\n      \"target\": 37876,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.2074074074074074,\n          \"y\": 0.6261904761904762,\n          \"width\": 0.25396825396825395,\n          \"height\": 0.16666666666666666\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 10,\n      \"type\": \"tap\",\n      \"attack\": 38847,\n      \"loopStart\": 39647,\n      \"target\": 41747,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.9523809523809523,\n          \"y\": 0.4666666666666667,\n          \"width\": 0.16084656084656085,\n          \"height\": 0.23333333333333334\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 11,\n      \"type\": \"tap\",\n      \"attack\": 42576,\n      \"loopStart\": 43276,\n      \"target\": 45526,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.5037037037037037,\n          \"y\": 0.6833333333333333,\n          \"width\": 0.2582010582010582,\n          \"height\": 0.14761904761904762\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 12,\n      \"type\": \"tap\",\n      \"attack\": 46513,\n      \"loopStart\": 47363,\n      \"target\": 49413,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.5037037037037037,\n          \"y\": 0.7452380952380953,\n          \"width\": 0.23703703703703702,\n          \"height\": 0.14761904761904762\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 13,\n      \"type\": \"tap\",\n      \"attack\": 50242,\n      \"loopStart\": 50942,\n      \"target\": 53192,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.10582010582010581,\n          \"y\": 0.8119047619047619,\n          \"width\": 0.26666666666666666,\n          \"height\": 0.1619047619047619\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 14,\n      \"type\": \"tap\",\n      \"attack\": 54075,\n      \"loopStart\": 54725,\n      \"target\": 57025,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.7068783068783069,\n          \"y\": 0.7690476190476191,\n          \"width\": 0.2751322751322751,\n          \"height\": 0.1\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 15,\n      \"type\": \"tap\",\n      \"attack\": 57701,\n      \"loopStart\": 58751,\n      \"target\": 60751,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.656084656084656,\n          \"y\": 0.8738095238095238,\n          \"width\": 0.17354497354497356,\n          \"height\": 0.1619047619047619\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 16,\n      \"type\": \"tap\",\n      \"attack\": 61534,\n      \"loopStart\": 62184,\n      \"target\": 64531,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.9566137566137566,\n          \"y\": 0.8928571428571429,\n          \"width\": 0.3216931216931217,\n          \"height\": 0.29523809523809524\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 17,\n      \"type\": \"tap\",\n      \"attack\": 65574,\n      \"loopStart\": 66220,\n      \"target\": 68473,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.9396825396825397,\n          \"y\": 0.9476190476190476,\n          \"width\": 0.30052910052910053,\n          \"height\": 0.16428571428571428\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 18,\n      \"type\": \"tap\",\n      \"attack\": 69407,\n      \"loopStart\": 70307,\n      \"target\": 72307,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.8,\n          \"y\": 0.8714285714285714,\n          \"width\": 0.2582010582010582,\n          \"height\": 0.15\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 19,\n      \"type\": \"tap\",\n      \"attack\": 73186,\n      \"loopStart\": 73786,\n      \"target\": 76136,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.9396825396825397,\n          \"y\": 0.9428571428571428,\n          \"width\": 0.30476190476190484,\n          \"height\": 0.14285714285714285\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 20,\n      \"type\": \"tap\",\n      \"attack\": 77283,\n      \"loopStart\": 77933,\n      \"target\": 80083,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.656084656084656,\n          \"y\": 0.930952380952381,\n          \"width\": 0.5417989417989418,\n          \"height\": 0.15\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 21,\n      \"type\": \"tap\",\n      \"attack\": 81734,\n      \"loopStart\": 82484,\n      \"target\": 84684,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.7576719576719577,\n          \"y\": 0.8666666666666667,\n          \"width\": 0.19894179894179895,\n          \"height\": 0.1619047619047619\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 22,\n      \"type\": \"tap\",\n      \"attack\": 85567,\n      \"loopStart\": 86417,\n      \"target\": 88517,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.8465608465608465,\n          \"y\": 0.8738095238095238,\n          \"width\": 0.1693121693121693,\n          \"height\": 0.1738095238095238\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 23,\n      \"type\": \"tap\",\n      \"attack\": 89296,\n      \"loopStart\": 90246,\n      \"target\": 92296,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.28359788359788357,\n          \"y\": 0.9714285714285714,\n          \"width\": 0.42328042328042326,\n          \"height\": 0.11666666666666667\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 24,\n      \"type\": \"tap\",\n      \"attack\": 93233,\n      \"loopStart\": 94183,\n      \"target\": 96183,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.7576719576719577,\n          \"y\": 0.9619047619047619,\n          \"width\": 0.3682539682539683,\n          \"height\": 0.10238095238095238\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 25,\n      \"type\": \"tap\",\n      \"attack\": 97066,\n      \"loopStart\": 97916,\n      \"target\": 100016,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.5502645502645502,\n          \"y\": 0.9428571428571428,\n          \"width\": 0.18624338624338624,\n          \"height\": 0.19047619047619047\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 26,\n      \"type\": \"tap\",\n      \"attack\": 100849,\n      \"loopStart\": 101499,\n      \"target\": 103699,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.050793650793650794,\n          \"y\": 0.8785714285714286,\n          \"width\": 0.18624338624338624,\n          \"height\": 0.17142857142857143\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 27,\n      \"type\": \"tap\",\n      \"attack\": 104524,\n      \"loopStart\": 105124,\n      \"target\": 107424,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.09312169312169312,\n          \"y\": 0.9642857142857143,\n          \"width\": 0.2920634920634921,\n          \"height\": 0.10714285714285714\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ]\n];\n      window.showUserGuide = false;\n      window.userGuideUrl = 'undefined';\n      window.userGuidePosition = {};\n      window.installAttributes = {\"x\":0.269510177064372,\"y\":0.007142857142857143,\"width\":0.4821611782227371,\"percentage\":true};\n      window.showFloatingMenu = true;\n      window.videoOrientation = 0;\n      window.disableUserFeedback = false;\n\n      window.hasEndCard = false;\n      window.endCardSettings = undefined;\n      \n      \n    </script>\n  </head>\n  <body>\n    <div id=\"mainContainer\">\n      <img id=\"loadingImage\" src=\"https://adcdn.zplayads.com/assets/prod/6ea73ab0-3cc4-11e8-a313-55140a049e95/load.jpg\" />\n      <div id=\"rotatedContainer\">\n\n        <img id=\"closeButton\" src=\"https://adcdn.zplayads.com/assets/images/x_button.png\"/>\n        <img id=\"restartButton\" src=\"https://adcdn.zplayads.com/assets/images/restart.png\"/>\n\n        <img id=\"installButton\" src=\"https://adcdn.zplayads.com/assets/prod/6ea73ab0-3cc4-11e8-a313-55140a049e95/downloadImage.png?key=468\" />\n\n        <video id=\"atmosPlayer\" webkit-playsinline playsinline muted preload=\"auto\" src=\"https://adcdn.zplayads.com/assets/prod/6ea73ab0-3cc4-11e8-a313-55140a049e95/transcoded_video_1500kbps.mp4\" poster=\"https://adcdn.zplayads.com/assets/prod/6ea73ab0-3cc4-11e8-a313-55140a049e95/load.jpg\" autoplay></video>\n        <audio id=\"bgMusicPlayer\" src=\"https://adcdn.zplayads.com/assets/prod/6ea73ab0-3cc4-11e8-a313-55140a049e95/bgMusic.mp3?key=744\" type=\"audio/mpeg\" loop></audio>\n\n        <video id=\"atmosPlayerEndCard\" webkit-playsinline playsinline muted preload=\"auto\" src=\"\" poster=\"https://adcdn.zplayads.com/assets/prod/6ea73ab0-3cc4-11e8-a313-55140a049e95/load.jpg\" style=\"z-index: -10;\"></video>\n\n        <canvas id=\"gestureDetector\"></canvas>\n        <canvas id=\"userFeedback\"></canvas>\n\n        <div id=\"floatingMenu\" class=\"simple\">\n          <span class=\"title\">¿ÉÍæµÄÃÔÄãÓÎÏ·</span><img alt=\"gamebox\" class=\"logo\" src=\"https://adcdn.zplayads.com/assets/images/zplayads_logo.png\"/>\n        </div>\n\n      </div>\n    </div>\n    \n    <script src=\"https://adcdn.zplayads.com/engine/prod/3.0.0/atmos.min.js\"></script>\n    \n  </body>\n</html>",
      "price": 30000000
    }
  ],
  "cur": "CNY"
}
```

#### 原生

##### 请求示例

```json
{
  "version": "1.0",
  "developer_token": "D0C85086-DC66-433E-9304-49EAB171D008",
  "need_https": 1,
  "app": {
    "app_id": "A650AB0D-7BFC-2A81-3066-D3170947C3DA",
    "app_name": "app_name",
    "bundle_id": "com.playableads.demo",
    "version": "1.0",
    "cat": "cat"
  },
  "device": {
    "model": "iphone",
    "manufacturer": "iphone",
    "brand": "apple",
    "plmn": "46001",
    "device_type": "phone",
    "adt": 1,
    "connection_type": "wifi",
    "carrier": 3,
    "orientation": 0,
    "mac": "",
    "imei": "",
    "android_id": "",
    "android_ad_id": "",
    "idfa": "123456789",
    "idfv": "",
    "openudid": "openudid",
    "language": "zh",
    "os_type": "ios",
    "os_version": "11.4.1",
    "screen": {
      "width": 123,
      "height": 234,
      "dpi": 2,
      "pxratio": 34567
    },
    "geo": {
      "lat": 34.567,
      "lon": 107.67,
      "horizontal_accu": 45,
      "vertical_accu": 56
    }
  },
  "user": {
    "id": "34ddd",
    "gender": 0,
    "age": 34,
    "keywords": ["45", "56", "abd"]
  },
  "ads": [
    {
      "unit_type": 3,
      "ad_unit_id": "25AED008-6B6F-BADB-F873-AE7CA61DFE98",
      "native": {
        "assets": [
          {
            "id": 1,
            "required": 0,
            "title": {
              "len": 5
            }
          },
          {
            "id": 2,
            "required": 1,
            "image": {
              "type": 3,
              "width": 345,
              "height": 234
            }
          },
          {
            "id": 3,
            "required": 1,
            "data": {
              "type": 2,
              "len": 34
            }
          }
        ]
      }
    }
  ]
}
```

##### 返回示例

```json
{
  "result": 0,
  "msg": "",
  "ads": [
    {
      "id": "6E4ADB48-6674-B91F-AE85-12E8CD21A847",
      "ad_unit_id": "25AED008-6B6F-BADB-F873-AE7CA61DFE98",
      "msg": "C0EB1023-8170-E612-5ABA-B437C26CC709",
      "app_bundle": "834878585",
      "target_url": "https://itunes.apple.com/cn/app/id834878585?mt=8",
      "target_url_type": 6,
      "playable_ads_html": "<!DOCTYPE html>\n<html>\n  <head>\n    <meta name=\"viewport\" content=\"user-scalable=no, width=device-width, initial-scale=1, maximum-scale=1\">\n    <title>Atmosplayer</title>\n    <meta charset=\"utf-8\"/>\n    <script>\n      window.gestures = [\n  [\n    {\n      \"id\": 0,\n      \"type\": \"tap\",\n      \"attack\": 0,\n      \"target\": 1999,\n      \"fullscreen\": true,\n      \"shapes\": [\n        {\n          \"type\": \"circle\",\n          \"x\": 0.42328042328042326,\n          \"y\": 0.23809523809523808,\n          \"radius\": 0.08465608465608465\n        }\n      ],\n      \"mandatory\": false,\n      \"tapDirection\": 1,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 1,\n      \"type\": \"tap\",\n      \"attack\": 3269,\n      \"loopStart\": 4368,\n      \"target\": 6519,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.5544973544973544,\n          \"y\": 0.5595238095238095,\n          \"width\": 0.33015873015873015,\n          \"height\": 0.15\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 2,\n      \"type\": \"tap\",\n      \"attack\": 7458,\n      \"loopStart\": 8355,\n      \"target\": 10357,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.6476190476190475,\n          \"y\": 0.5952380952380952,\n          \"width\": 0.3386243386243386,\n          \"height\": 0.20714285714285716\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 3,\n      \"type\": \"tap\",\n      \"attack\": 11913,\n      \"loopStart\": 12863,\n      \"target\": 14913,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.45291005291005293,\n          \"y\": 0.5880952380952381,\n          \"width\": 0.182010582010582,\n          \"height\": 0.20952380952380953\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 4,\n      \"type\": \"tap\",\n      \"attack\": 15849,\n      \"loopStart\": 16643,\n      \"target\": 18849,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.30052910052910053,\n          \"y\": 0.5904761904761905,\n          \"width\": 0.2455026455026455,\n          \"height\": 0.19047619047619047\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 5,\n      \"type\": \"tap\",\n      \"attack\": 19786,\n      \"loopStart\": 20736,\n      \"target\": 22736,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.35555555555555557,\n          \"y\": 0.5952380952380952,\n          \"width\": 0.16507936507936508,\n          \"height\": 0.20952380952380953\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 6,\n      \"type\": \"tap\",\n      \"attack\": 23722,\n      \"loopStart\": 24472,\n      \"target\": 26572,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.09312169312169312,\n          \"y\": 0.4976190476190476,\n          \"width\": 0.30052910052910053,\n          \"height\": 0.14523809523809525\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 7,\n      \"type\": \"tap\",\n      \"attack\": 27348,\n      \"loopStart\": 28448,\n      \"target\": 30398,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.10158730158730159,\n          \"y\": 0.530952380952381,\n          \"width\": 0.31322751322751324,\n          \"height\": 0.1\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 8,\n      \"type\": \"tap\",\n      \"attack\": 31284,\n      \"loopStart\": 32134,\n      \"target\": 34129,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.15661375661375662,\n          \"y\": 0.6238095238095238,\n          \"width\": 0.1693121693121693,\n          \"height\": 0.16666666666666666\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 9,\n      \"type\": \"tap\",\n      \"attack\": 34776,\n      \"loopStart\": 35676,\n      \"target\": 37876,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.2074074074074074,\n          \"y\": 0.6261904761904762,\n          \"width\": 0.25396825396825395,\n          \"height\": 0.16666666666666666\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 10,\n      \"type\": \"tap\",\n      \"attack\": 38847,\n      \"loopStart\": 39647,\n      \"target\": 41747,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.9523809523809523,\n          \"y\": 0.4666666666666667,\n          \"width\": 0.16084656084656085,\n          \"height\": 0.23333333333333334\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 11,\n      \"type\": \"tap\",\n      \"attack\": 42576,\n      \"loopStart\": 43276,\n      \"target\": 45526,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.5037037037037037,\n          \"y\": 0.6833333333333333,\n          \"width\": 0.2582010582010582,\n          \"height\": 0.14761904761904762\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 12,\n      \"type\": \"tap\",\n      \"attack\": 46513,\n      \"loopStart\": 47363,\n      \"target\": 49413,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.5037037037037037,\n          \"y\": 0.7452380952380953,\n          \"width\": 0.23703703703703702,\n          \"height\": 0.14761904761904762\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 13,\n      \"type\": \"tap\",\n      \"attack\": 50242,\n      \"loopStart\": 50942,\n      \"target\": 53192,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.10582010582010581,\n          \"y\": 0.8119047619047619,\n          \"width\": 0.26666666666666666,\n          \"height\": 0.1619047619047619\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 14,\n      \"type\": \"tap\",\n      \"attack\": 54075,\n      \"loopStart\": 54725,\n      \"target\": 57025,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.7068783068783069,\n          \"y\": 0.7690476190476191,\n          \"width\": 0.2751322751322751,\n          \"height\": 0.1\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 15,\n      \"type\": \"tap\",\n      \"attack\": 57701,\n      \"loopStart\": 58751,\n      \"target\": 60751,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.656084656084656,\n          \"y\": 0.8738095238095238,\n          \"width\": 0.17354497354497356,\n          \"height\": 0.1619047619047619\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 16,\n      \"type\": \"tap\",\n      \"attack\": 61534,\n      \"loopStart\": 62184,\n      \"target\": 64531,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.9566137566137566,\n          \"y\": 0.8928571428571429,\n          \"width\": 0.3216931216931217,\n          \"height\": 0.29523809523809524\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 17,\n      \"type\": \"tap\",\n      \"attack\": 65574,\n      \"loopStart\": 66220,\n      \"target\": 68473,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.9396825396825397,\n          \"y\": 0.9476190476190476,\n          \"width\": 0.30052910052910053,\n          \"height\": 0.16428571428571428\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 18,\n      \"type\": \"tap\",\n      \"attack\": 69407,\n      \"loopStart\": 70307,\n      \"target\": 72307,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.8,\n          \"y\": 0.8714285714285714,\n          \"width\": 0.2582010582010582,\n          \"height\": 0.15\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 19,\n      \"type\": \"tap\",\n      \"attack\": 73186,\n      \"loopStart\": 73786,\n      \"target\": 76136,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.9396825396825397,\n          \"y\": 0.9428571428571428,\n          \"width\": 0.30476190476190484,\n          \"height\": 0.14285714285714285\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 20,\n      \"type\": \"tap\",\n      \"attack\": 77283,\n      \"loopStart\": 77933,\n      \"target\": 80083,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.656084656084656,\n          \"y\": 0.930952380952381,\n          \"width\": 0.5417989417989418,\n          \"height\": 0.15\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 21,\n      \"type\": \"tap\",\n      \"attack\": 81734,\n      \"loopStart\": 82484,\n      \"target\": 84684,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.7576719576719577,\n          \"y\": 0.8666666666666667,\n          \"width\": 0.19894179894179895,\n          \"height\": 0.1619047619047619\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 22,\n      \"type\": \"tap\",\n      \"attack\": 85567,\n      \"loopStart\": 86417,\n      \"target\": 88517,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.8465608465608465,\n          \"y\": 0.8738095238095238,\n          \"width\": 0.1693121693121693,\n          \"height\": 0.1738095238095238\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 23,\n      \"type\": \"tap\",\n      \"attack\": 89296,\n      \"loopStart\": 90246,\n      \"target\": 92296,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.28359788359788357,\n          \"y\": 0.9714285714285714,\n          \"width\": 0.42328042328042326,\n          \"height\": 0.11666666666666667\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 24,\n      \"type\": \"tap\",\n      \"attack\": 93233,\n      \"loopStart\": 94183,\n      \"target\": 96183,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.7576719576719577,\n          \"y\": 0.9619047619047619,\n          \"width\": 0.3682539682539683,\n          \"height\": 0.10238095238095238\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 25,\n      \"type\": \"tap\",\n      \"attack\": 97066,\n      \"loopStart\": 97916,\n      \"target\": 100016,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.5502645502645502,\n          \"y\": 0.9428571428571428,\n          \"width\": 0.18624338624338624,\n          \"height\": 0.19047619047619047\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 26,\n      \"type\": \"tap\",\n      \"attack\": 100849,\n      \"loopStart\": 101499,\n      \"target\": 103699,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.050793650793650794,\n          \"y\": 0.8785714285714286,\n          \"width\": 0.18624338624338624,\n          \"height\": 0.17142857142857143\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 27,\n      \"type\": \"tap\",\n      \"attack\": 104524,\n      \"loopStart\": 105124,\n      \"target\": 107424,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.09312169312169312,\n          \"y\": 0.9642857142857143,\n          \"width\": 0.2920634920634921,\n          \"height\": 0.10714285714285714\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ]\n];\n      window.showUserGuide = false;\n      window.userGuideUrl = 'undefined';\n      window.userGuidePosition = {};\n      window.installAttributes = {\"x\":0.269510177064372,\"y\":0.007142857142857143,\"width\":0.4821611782227371,\"percentage\":true};\n      window.showFloatingMenu = true;\n      window.videoOrientation = 0;\n      window.disableUserFeedback = false;\n\n      window.hasEndCard = false;\n      window.endCardSettings = undefined;\n      \n      \n    </script>\n  </head>\n  <body>\n    <div id=\"mainContainer\">\n      <img id=\"loadingImage\" src=\"https://adcdn.zplayads.com/assets/prod/6ea73ab0-3cc4-11e8-a313-55140a049e95/load.jpg\" />\n      <div id=\"rotatedContainer\">\n\n        <img id=\"closeButton\" src=\"https://adcdn.zplayads.com/assets/images/x_button.png\"/>\n        <img id=\"restartButton\" src=\"https://adcdn.zplayads.com/assets/images/restart.png\"/>\n\n        <img id=\"installButton\" src=\"https://adcdn.zplayads.com/assets/prod/6ea73ab0-3cc4-11e8-a313-55140a049e95/downloadImage.png?key=468\" />\n\n        <video id=\"atmosPlayer\" webkit-playsinline playsinline muted preload=\"auto\" src=\"https://adcdn.zplayads.com/assets/prod/6ea73ab0-3cc4-11e8-a313-55140a049e95/transcoded_video_1500kbps.mp4\" poster=\"https://adcdn.zplayads.com/assets/prod/6ea73ab0-3cc4-11e8-a313-55140a049e95/load.jpg\" autoplay></video>\n        <audio id=\"bgMusicPlayer\" src=\"https://adcdn.zplayads.com/assets/prod/6ea73ab0-3cc4-11e8-a313-55140a049e95/bgMusic.mp3?key=744\" type=\"audio/mpeg\" loop></audio>\n\n        <video id=\"atmosPlayerEndCard\" webkit-playsinline playsinline muted preload=\"auto\" src=\"\" poster=\"https://adcdn.zplayads.com/assets/prod/6ea73ab0-3cc4-11e8-a313-55140a049e95/load.jpg\" style=\"z-index: -10;\"></video>\n\n        <canvas id=\"gestureDetector\"></canvas>\n        <canvas id=\"userFeedback\"></canvas>\n\n        <div id=\"floatingMenu\" class=\"simple\">\n          <span class=\"title\">¿ÉÍæµÄÃÔÄãÓÎÏ·</span><img alt=\"gamebox\" class=\"logo\" src=\"https://adcdn.zplayads.com/assets/images/zplayads_logo.png\"/>\n        </div>\n\n      </div>\n    </div>\n    \n    <script src=\"https://adcdn.zplayads.com/engine/prod/3.0.0/atmos.min.js\"></script>\n    \n  </body>\n</html>",
      "price": 30000000,
      "native": {
        "imp_tracker": [
          "https://pa-engine.zplayads.com/v1/tracking?ab_test_id=A011A3BB-9316-08D6-06DD-3DADFA6B73C1&ab_test_object_group_id=default&ad_id=6E4ADB48-6674-B91F-AE85-12E8CD21A847&ad_unit_id=25AED008-6B6F-BADB-F873-AE7CA61DFE98&app_id=A650AB0D-7BFC-2A81-3066-D3170947C3DA&brand=&bundle_id=bundle_id&channel_id=&channel_share_rate=0&client_id=73AB1CDF-009E-130C-4A15-94901D3470DE&creatives_id=C0EB1023-8170-E612-5ABA-B437C26CC709&developer_share_rate=70&device_model=iphone&device_type=phone&engine_events=&idfa=123456789&industry_id=&last_status=0&network_connection_type=wifi&order_id=8D42D892-AF3D-FA88-76F2-461A5B6E427E&os=iOS&os_version=11.4.1&pay_by=cpi&pay_event=install&predictive_cpm_cipher=a1ab3e958035bb00b4f5beb2&predictive_cpm_usd_cipher=&promotion_app_id=8B6BC1BB-368A-6C77-735A-929E38E20D9F&request_id=bfhtftfhefb0idufd2l0&settlement_price_cny=0&settlement_price_usd=0&tracking_type=native_present&unit_price_cny=2000000&unit_price_usd=287166"
        ],
        "assets": [
          {
            "id": 1,
            "title": {
              "text": "PopStar!"
            },
            "image": {},
            "data": {}
          },
          {
            "id": 2,
            "required": 1,
            "title": {},
            "image": {
              "width": 471,
              "height": 265,
              "url": "https://pa-cloud.zplayads.com/alfred/static/2018/10/18/5bc835055c05b.jpg"
            },
            "data": {}
          },
          {
            "id": 3,
            "required": 1,
            "title": {},
            "image": {},
            "data": {
              "label": "2",
              "value": "PopStar! ¨C The most fun puzzle game in the world!"
            }
          }
        ],
        "link": {
          "app_bundle": "834878585",
          "click_tracker": [
            "https://pa-engine.zplayads.com/v1/tracking?ab_test_id=A011A3BB-9316-08D6-06DD-3DADFA6B73C1&ab_test_object_group_id=default&ad_id=6E4ADB48-6674-B91F-AE85-12E8CD21A847&ad_unit_id=25AED008-6B6F-BADB-F873-AE7CA61DFE98&app_id=A650AB0D-7BFC-2A81-3066-D3170947C3DA&brand=&bundle_id=bundle_id&channel_id=&channel_share_rate=0&client_id=73AB1CDF-009E-130C-4A15-94901D3470DE&creatives_id=C0EB1023-8170-E612-5ABA-B437C26CC709&developer_share_rate=70&device_model=iphone&device_type=phone&engine_events=&idfa=123456789&industry_id=&last_status=0&network_connection_type=wifi&order_id=8D42D892-AF3D-FA88-76F2-461A5B6E427E&os=iOS&os_version=11.4.1&pay_by=cpi&pay_event=install&predictive_cpm_cipher=a1ab3e958035bb00b4f5beb2&predictive_cpm_usd_cipher=&promotion_app_id=8B6BC1BB-368A-6C77-735A-929E38E20D9F&request_id=bfhtftfhefb0idufd2l0&settlement_price_cny=0&settlement_price_usd=0&tracking_type=click_from_native_button&unit_price_cny=2000000&unit_price_usd=287166",
            "null"
          ],
          "target_url": "https://itunes.apple.com/cn/app/id834878585?mt=8",
          "target_url_type": 6
        }
      }
    }
  ],
  "cur": "CNY"
}
```

#### 激励视频

##### 请求示例

```json
{
  "version": "1.0",
  "developer_token": "D0C85086-DC66-433E-9304-49EAB171D008",
  "need_https": 1,
  "app": {
    "app_id": "A650AB0D-7BFC-2A81-3066-D3170947C3DA",
    "app_name": "app_name",
    "bundle_id": "com.playableads.demo",
    "version": "1.0",
    "cat": "cat"
  },
  "device": {
    "model": "iphone",
    "manufacturer": "iphone",
    "brand": "apple",
    "plmn": "46001",
    "device_type": "phone",
    "adt": 1,
    "connection_type": "wifi",
    "carrier": 3,
    "orientation": 0,
    "mac": "",
    "imei": "",
    "android_id": "",
    "android_ad_id": "",
    "idfa": "123456789",
    "idfv": "",
    "openudid": "openudid",
    "language": "zh",
    "os_type": "ios",
    "os_version": "11.4.1",
    "screen": {
      "width": 123,
      "height": 234,
      "dpi": 2,
      "pxratio": 34567
    },
    "geo": {
      "lat": 34.567,
      "lon": 107.67,
      "horizontal_accu": 45,
      "vertical_accu": 56
    }
  },
  "user": {
    "id": "34ddd",
    "gender": 0,
    "age": 34,
    "keywords": ["45", "56", "abd"]
  },
  "ads": [
    {
      "unit_type": 4,
      "ad_unit_id": "BAE5DAAC-04A2-2591-D5B0-38FA846E45E7"
    }
  ]
}
```

##### 返回示例

```json
{
  "result": 0,
  "msg": "",
  "ads": [
    {
      "id": "6E4ADB48-6674-B91F-AE85-12E8CD21A847",
      "ad_unit_id": "BAE5DAAC-04A2-2591-D5B0-38FA846E45E7",
      "msg": "C0EB1023-8170-E612-5ABA-B437C26CC709",
      "app_bundle": "834878585",
      "target_url": "https://itunes.apple.com/cn/app/id834878585?mt=8",
      "target_url_type": 6,
      "playable_ads_html": "<!DOCTYPE html>\n<html>\n  <head>\n    <meta name=\"viewport\" content=\"user-scalable=no, width=device-width, initial-scale=1, maximum-scale=1\">\n    <title>Atmosplayer</title>\n    <meta charset=\"utf-8\"/>\n    <script>\n      window.gestures = [\n  [\n    {\n      \"id\": 0,\n      \"type\": \"tap\",\n      \"attack\": 0,\n      \"target\": 1999,\n      \"fullscreen\": true,\n      \"shapes\": [\n        {\n          \"type\": \"circle\",\n          \"x\": 0.42328042328042326,\n          \"y\": 0.23809523809523808,\n          \"radius\": 0.08465608465608465\n        }\n      ],\n      \"mandatory\": false,\n      \"tapDirection\": 1,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 1,\n      \"type\": \"tap\",\n      \"attack\": 3269,\n      \"loopStart\": 4368,\n      \"target\": 6519,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.5544973544973544,\n          \"y\": 0.5595238095238095,\n          \"width\": 0.33015873015873015,\n          \"height\": 0.15\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 2,\n      \"type\": \"tap\",\n      \"attack\": 7458,\n      \"loopStart\": 8355,\n      \"target\": 10357,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.6476190476190475,\n          \"y\": 0.5952380952380952,\n          \"width\": 0.3386243386243386,\n          \"height\": 0.20714285714285716\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 3,\n      \"type\": \"tap\",\n      \"attack\": 11913,\n      \"loopStart\": 12863,\n      \"target\": 14913,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.45291005291005293,\n          \"y\": 0.5880952380952381,\n          \"width\": 0.182010582010582,\n          \"height\": 0.20952380952380953\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 4,\n      \"type\": \"tap\",\n      \"attack\": 15849,\n      \"loopStart\": 16643,\n      \"target\": 18849,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.30052910052910053,\n          \"y\": 0.5904761904761905,\n          \"width\": 0.2455026455026455,\n          \"height\": 0.19047619047619047\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 5,\n      \"type\": \"tap\",\n      \"attack\": 19786,\n      \"loopStart\": 20736,\n      \"target\": 22736,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.35555555555555557,\n          \"y\": 0.5952380952380952,\n          \"width\": 0.16507936507936508,\n          \"height\": 0.20952380952380953\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 6,\n      \"type\": \"tap\",\n      \"attack\": 23722,\n      \"loopStart\": 24472,\n      \"target\": 26572,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.09312169312169312,\n          \"y\": 0.4976190476190476,\n          \"width\": 0.30052910052910053,\n          \"height\": 0.14523809523809525\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 7,\n      \"type\": \"tap\",\n      \"attack\": 27348,\n      \"loopStart\": 28448,\n      \"target\": 30398,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.10158730158730159,\n          \"y\": 0.530952380952381,\n          \"width\": 0.31322751322751324,\n          \"height\": 0.1\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 8,\n      \"type\": \"tap\",\n      \"attack\": 31284,\n      \"loopStart\": 32134,\n      \"target\": 34129,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.15661375661375662,\n          \"y\": 0.6238095238095238,\n          \"width\": 0.1693121693121693,\n          \"height\": 0.16666666666666666\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 9,\n      \"type\": \"tap\",\n      \"attack\": 34776,\n      \"loopStart\": 35676,\n      \"target\": 37876,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.2074074074074074,\n          \"y\": 0.6261904761904762,\n          \"width\": 0.25396825396825395,\n          \"height\": 0.16666666666666666\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 10,\n      \"type\": \"tap\",\n      \"attack\": 38847,\n      \"loopStart\": 39647,\n      \"target\": 41747,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.9523809523809523,\n          \"y\": 0.4666666666666667,\n          \"width\": 0.16084656084656085,\n          \"height\": 0.23333333333333334\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 11,\n      \"type\": \"tap\",\n      \"attack\": 42576,\n      \"loopStart\": 43276,\n      \"target\": 45526,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.5037037037037037,\n          \"y\": 0.6833333333333333,\n          \"width\": 0.2582010582010582,\n          \"height\": 0.14761904761904762\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 12,\n      \"type\": \"tap\",\n      \"attack\": 46513,\n      \"loopStart\": 47363,\n      \"target\": 49413,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.5037037037037037,\n          \"y\": 0.7452380952380953,\n          \"width\": 0.23703703703703702,\n          \"height\": 0.14761904761904762\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 13,\n      \"type\": \"tap\",\n      \"attack\": 50242,\n      \"loopStart\": 50942,\n      \"target\": 53192,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.10582010582010581,\n          \"y\": 0.8119047619047619,\n          \"width\": 0.26666666666666666,\n          \"height\": 0.1619047619047619\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 14,\n      \"type\": \"tap\",\n      \"attack\": 54075,\n      \"loopStart\": 54725,\n      \"target\": 57025,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.7068783068783069,\n          \"y\": 0.7690476190476191,\n          \"width\": 0.2751322751322751,\n          \"height\": 0.1\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 15,\n      \"type\": \"tap\",\n      \"attack\": 57701,\n      \"loopStart\": 58751,\n      \"target\": 60751,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.656084656084656,\n          \"y\": 0.8738095238095238,\n          \"width\": 0.17354497354497356,\n          \"height\": 0.1619047619047619\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 16,\n      \"type\": \"tap\",\n      \"attack\": 61534,\n      \"loopStart\": 62184,\n      \"target\": 64531,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.9566137566137566,\n          \"y\": 0.8928571428571429,\n          \"width\": 0.3216931216931217,\n          \"height\": 0.29523809523809524\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 17,\n      \"type\": \"tap\",\n      \"attack\": 65574,\n      \"loopStart\": 66220,\n      \"target\": 68473,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.9396825396825397,\n          \"y\": 0.9476190476190476,\n          \"width\": 0.30052910052910053,\n          \"height\": 0.16428571428571428\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 18,\n      \"type\": \"tap\",\n      \"attack\": 69407,\n      \"loopStart\": 70307,\n      \"target\": 72307,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.8,\n          \"y\": 0.8714285714285714,\n          \"width\": 0.2582010582010582,\n          \"height\": 0.15\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 19,\n      \"type\": \"tap\",\n      \"attack\": 73186,\n      \"loopStart\": 73786,\n      \"target\": 76136,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.9396825396825397,\n          \"y\": 0.9428571428571428,\n          \"width\": 0.30476190476190484,\n          \"height\": 0.14285714285714285\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 20,\n      \"type\": \"tap\",\n      \"attack\": 77283,\n      \"loopStart\": 77933,\n      \"target\": 80083,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.656084656084656,\n          \"y\": 0.930952380952381,\n          \"width\": 0.5417989417989418,\n          \"height\": 0.15\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 21,\n      \"type\": \"tap\",\n      \"attack\": 81734,\n      \"loopStart\": 82484,\n      \"target\": 84684,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.7576719576719577,\n          \"y\": 0.8666666666666667,\n          \"width\": 0.19894179894179895,\n          \"height\": 0.1619047619047619\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 22,\n      \"type\": \"tap\",\n      \"attack\": 85567,\n      \"loopStart\": 86417,\n      \"target\": 88517,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.8465608465608465,\n          \"y\": 0.8738095238095238,\n          \"width\": 0.1693121693121693,\n          \"height\": 0.1738095238095238\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 23,\n      \"type\": \"tap\",\n      \"attack\": 89296,\n      \"loopStart\": 90246,\n      \"target\": 92296,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.28359788359788357,\n          \"y\": 0.9714285714285714,\n          \"width\": 0.42328042328042326,\n          \"height\": 0.11666666666666667\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 24,\n      \"type\": \"tap\",\n      \"attack\": 93233,\n      \"loopStart\": 94183,\n      \"target\": 96183,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.7576719576719577,\n          \"y\": 0.9619047619047619,\n          \"width\": 0.3682539682539683,\n          \"height\": 0.10238095238095238\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 25,\n      \"type\": \"tap\",\n      \"attack\": 97066,\n      \"loopStart\": 97916,\n      \"target\": 100016,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.5502645502645502,\n          \"y\": 0.9428571428571428,\n          \"width\": 0.18624338624338624,\n          \"height\": 0.19047619047619047\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 26,\n      \"type\": \"tap\",\n      \"attack\": 100849,\n      \"loopStart\": 101499,\n      \"target\": 103699,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.050793650793650794,\n          \"y\": 0.8785714285714286,\n          \"width\": 0.18624338624338624,\n          \"height\": 0.17142857142857143\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ],\n  [\n    {\n      \"id\": 27,\n      \"type\": \"tap\",\n      \"attack\": 104524,\n      \"loopStart\": 105124,\n      \"target\": 107424,\n      \"fullscreen\": false,\n      \"shapes\": [\n        {\n          \"type\": \"square\",\n          \"x\": 0.09312169312169312,\n          \"y\": 0.9642857142857143,\n          \"width\": 0.2920634920634921,\n          \"height\": 0.10714285714285714\n        }\n      ],\n      \"mandatory\": true,\n      \"tapDirection\": 2,\n      \"loop\": true,\n      \"tapCount\": 1\n    }\n  ]\n];\n      window.showUserGuide = false;\n      window.userGuideUrl = 'undefined';\n      window.userGuidePosition = {};\n      window.installAttributes = {\"x\":0.269510177064372,\"y\":0.007142857142857143,\"width\":0.4821611782227371,\"percentage\":true};\n      window.showFloatingMenu = true;\n      window.videoOrientation = 0;\n      window.disableUserFeedback = false;\n\n      window.hasEndCard = false;\n      window.endCardSettings = undefined;\n      \n      \n    </script>\n  </head>\n  <body>\n    <div id=\"mainContainer\">\n      <img id=\"loadingImage\" src=\"https://adcdn.zplayads.com/assets/prod/6ea73ab0-3cc4-11e8-a313-55140a049e95/load.jpg\" />\n      <div id=\"rotatedContainer\">\n\n        <img id=\"closeButton\" src=\"https://adcdn.zplayads.com/assets/images/x_button.png\"/>\n        <img id=\"restartButton\" src=\"https://adcdn.zplayads.com/assets/images/restart.png\"/>\n\n        <img id=\"installButton\" src=\"https://adcdn.zplayads.com/assets/prod/6ea73ab0-3cc4-11e8-a313-55140a049e95/downloadImage.png?key=468\" />\n\n        <video id=\"atmosPlayer\" webkit-playsinline playsinline muted preload=\"auto\" src=\"https://adcdn.zplayads.com/assets/prod/6ea73ab0-3cc4-11e8-a313-55140a049e95/transcoded_video_1500kbps.mp4\" poster=\"https://adcdn.zplayads.com/assets/prod/6ea73ab0-3cc4-11e8-a313-55140a049e95/load.jpg\" autoplay></video>\n        <audio id=\"bgMusicPlayer\" src=\"https://adcdn.zplayads.com/assets/prod/6ea73ab0-3cc4-11e8-a313-55140a049e95/bgMusic.mp3?key=744\" type=\"audio/mpeg\" loop></audio>\n\n        <video id=\"atmosPlayerEndCard\" webkit-playsinline playsinline muted preload=\"auto\" src=\"\" poster=\"https://adcdn.zplayads.com/assets/prod/6ea73ab0-3cc4-11e8-a313-55140a049e95/load.jpg\" style=\"z-index: -10;\"></video>\n\n        <canvas id=\"gestureDetector\"></canvas>\n        <canvas id=\"userFeedback\"></canvas>\n\n        <div id=\"floatingMenu\" class=\"simple\">\n          <span class=\"title\">¿ÉÍæµÄÃÔÄãÓÎÏ·</span><img alt=\"gamebox\" class=\"logo\" src=\"https://adcdn.zplayads.com/assets/images/zplayads_logo.png\"/>\n        </div>\n\n      </div>\n    </div>\n    \n    <script src=\"https://adcdn.zplayads.com/engine/prod/3.0.0/atmos.min.js\"></script>\n    \n  </body>\n</html>",
      "price": 30000000
    }
  ],
  "cur": "CNY"
}
```

### Android

#### 插屏

##### 请求示例

```json
{
  "version": "1.0",
  "developer_token": "D0C85086-DC66-433E-9304-49EAB171D008",
  "need_https": 1,
  "app": {
    "app_id": "5C5419C7-A2DE-88BC-A311-C3E7A646F6AF",
    "app_name": "app_name",
    "bundle_id": "com.playableads.demo",
    "version": "1.0",
    "cat": "cat"
  },
  "device": {
    "model": "COL-AL10",
    "manufacturer": "HONOR",
    "brand": "HONOR",
    "plmn": "46001",
    "device_type": "phone",
    "adt": 1,
    "connection_type": "wifi",
    "carrier": 3,
    "orientation": 0,
    "mac": "28b92b0dde49cff7190841686960c6bc",
    "imei": "6cd5c276d3f6ce4205dde5b1bf913361",
    "android_id": "adf3b4675742e11a73db503d1273d860",
    "android_ad_id": "600c8c48-afca-42b8-89e5-4612c086c3cc",
    "idfa": "",
    "idfv": "",
    "openudid": "openudid",
    "language": "zh",
    "os_type": "android",
    "os_version": "7.4.1",
    "screen": {
      "width": 123,
      "height": 234,
      "dpi": 2,
      "pxratio": 34567
    },
    "geo": {
      "lat": 34.567,
      "lon": 107.67,
      "horizontal_accu": 45,
      "vertical_accu": 56
    }
  },
  "user": {
    "id": "34ddd",
    "gender": 0,
    "age": 34,
    "keywords": ["45", "56", "abd"]
  },
  "ads": [
    {
      "unit_type": 1,
      "ad_unit_id": "19393189-C4EB-3886-60B9-13B39407064E"
    }
  ]
}
```

##### 返回示例

```json
{
  "result": 0,
  "msg": "",
  "ads": [
    {
      "id": "476FC7D0-C133-42F5-ED04-20F8C2BF5882",
      "ad_unit_id": "19393189-C4EB-3886-60B9-13B39407064E",
      "msg": "9D7833A2-B939-16F0-A36C-C4F06518B8A0",
      "app_bundle": "0",
      "target_url": "https://play.google.com/store/apps/details?id=com.zplay.beatracer",
      "target_url_type": 6,
      "playable_ads_html": "<!DOCTYPE html>\n<html>\n  <head>\n    <meta name=\"viewport\" content=\"user-scalable=no, width=device-width, initial-scale=1, maximum-scale=1\">\n    <title>Atmosplayer</title>\n    <meta charset=\"utf-8\"/>\n    <script>\n      window.gestures = [\n  [\n    {\n      \"id\": 0,\n      \"type\": \"swipe\",\n      \"attack\": 1,\n      \"loopStart\": 551,\n      \"target\": 6651,\n      \"fullscreen\": true,\n      \"shapes\": [\n        {\n          \"type\": \"circle\",\n          \"x\": 0.42328042328042326,\n          \"y\": 0.23809523809523808,\n          \"radius\": 0.08465608465608465\n        }\n      ],\n      \"mandatory\": true,\n      \"swipeDirection\": \"LEFT\",\n      \"loop\": true\n    }\n  ],\n  [\n    {\n      \"id\": 1,\n      \"type\": \"swipe\",\n      \"attack\": 9049,\n      \"loopStart\": 9499,\n      \"target\": 14449,\n      \"fullscreen\": true,\n      \"shapes\": [\n        {\n          \"type\": \"circle\",\n          \"x\": 0.42328042328042326,\n          \"y\": 0.23809523809523808,\n          \"radius\": 0.08465608465608465\n        }\n      ],\n      \"mandatory\": true,\n      \"swipeDirection\": \"RIGHT\",\n      \"loop\": true\n    }\n  ],\n  [\n    {\n      \"id\": 2,\n      \"type\": \"swipe\",\n      \"attack\": 18060,\n      \"loopStart\": 18710,\n      \"target\": 23860,\n      \"fullscreen\": true,\n      \"shapes\": [\n        {\n          \"type\": \"circle\",\n          \"x\": 0.42328042328042326,\n          \"y\": 0.23809523809523808,\n          \"radius\": 0.08465608465608465\n        }\n      ],\n      \"mandatory\": true,\n      \"swipeDirection\": \"UP\",\n      \"loop\": true\n    }\n  ],\n  [\n    {\n      \"id\": 3,\n      \"type\": \"swipe\",\n      \"attack\": 28738,\n      \"loopStart\": 30288,\n      \"target\": 35036,\n      \"fullscreen\": true,\n      \"shapes\": [\n        {\n          \"type\": \"circle\",\n          \"x\": 0.42328042328042326,\n          \"y\": 0.23809523809523808,\n          \"radius\": 0.08465608465608465\n        }\n      ],\n      \"mandatory\": true,\n      \"swipeDirection\": \"DOWN\",\n      \"loop\": true\n    }\n  ],\n  [\n    {\n      \"id\": 4,\n      \"type\": \"tap\",\n      \"attack\": 38506,\n      \"target\": 40100,\n      \"fullscreen\": true,\n      \"shapes\": [\n        {\n          \"type\": \"circle\",\n          \"x\": 0.42328042328042326,\n          \"y\": 0.23809523809523808,\n          \"radius\": 0.08465608465608465\n        }\n      ],\n      \"mandatory\": false,\n      \"tapDirection\": 1,\n      \"tapCount\": 1\n    }\n  ]\n];\n      window.showUserGuide = false;\n      window.userGuideUrl = 'undefined';\n      window.userGuidePosition = {};\n      window.installAttributes = {\"x\":0.2779827900049644,\"y\":0.04047619047619048,\"width\":0.49487009763362566,\"percentage\":true};\n      window.showFloatingMenu = true;\n      window.videoOrientation = 0;\n      window.disableUserFeedback = false;\n\n      window.hasEndCard = false;\n      window.endCardSettings = undefined;\n      \n      \n    </script>\n  </head>\n  <body>\n    <div id=\"mainContainer\">\n      <img id=\"loadingImage\" src=\"https://adcdn.zplayads.com/assets/prod/63479990-3d68-11e8-a313-55140a049e95/load.jpg\" />\n      <div id=\"rotatedContainer\">\n\n        <img id=\"closeButton\" src=\"https://adcdn.zplayads.com/assets/images/x_button.png\"/>\n        <img id=\"restartButton\" src=\"https://adcdn.zplayads.com/assets/images/restart.png\"/>\n\n        <img id=\"installButton\" src=\"https://adcdn.zplayads.com/assets/prod/63479990-3d68-11e8-a313-55140a049e95/downloadImage.png?key=641\" />\n\n        <video id=\"atmosPlayer\" webkit-playsinline playsinline muted preload=\"auto\" src=\"https://adcdn.zplayads.com/assets/prod/63479990-3d68-11e8-a313-55140a049e95/transcoded_video_1500kbps.mp4\" poster=\"https://adcdn.zplayads.com/assets/prod/63479990-3d68-11e8-a313-55140a049e95/load.jpg\" autoplay></video>\n        <audio id=\"bgMusicPlayer\" src=\"https://adcdn.zplayads.com/assets/prod/63479990-3d68-11e8-a313-55140a049e95/bgMusic.mp3?key=284\" type=\"audio/mpeg\" loop></audio>\n\n        <video id=\"atmosPlayerEndCard\" webkit-playsinline playsinline muted preload=\"auto\" src=\"\" poster=\"https://adcdn.zplayads.com/assets/prod/63479990-3d68-11e8-a313-55140a049e95/load.jpg\" style=\"z-index: -10;\"></video>\n\n        <canvas id=\"gestureDetector\"></canvas>\n        <canvas id=\"userFeedback\"></canvas>\n\n        <div id=\"floatingMenu\" class=\"simple\">\n          <span class=\"title\">¿ÉÍæµÄÃÔÄãÓÎÏ·</span><img alt=\"gamebox\" class=\"logo\" src=\"https://adcdn.zplayads.com/assets/images/zplayads_logo.png\"/>\n        </div>\n\n      </div>\n    </div>\n    \n    <script src=\"https://adcdn.zplayads.com/engine/prod/3.0.0/atmos.min.js\"></script>\n    \n  </body>\n</html>",
      "price": 30000000
    }
  ],
  "cur": "CNY"
}
```

#### 原生

##### 请求示例

```json
{
  "version": "1.0",
  "developer_token": "D0C85086-DC66-433E-9304-49EAB171D008",
  "need_https": 1,
  "app": {
    "app_id": "5C5419C7-A2DE-88BC-A311-C3E7A646F6AF",
    "app_name": "app_name",
    "bundle_id": "com.playableads.demo",
    "version": "1.0",
    "cat": "cat"
  },
  "device": {
    "model": "COL-AL10",
    "manufacturer": "HONOR",
    "brand": "HONOR",
    "plmn": "46001",
    "device_type": "phone",
    "adt": 1,
    "connection_type": "wifi",
    "carrier": 3,
    "orientation": 0,
    "mac": "28b92b0dde49cff7190841686960c6bc",
    "imei": "6cd5c276d3f6ce4205dde5b1bf913361",
    "android_id": "adf3b4675742e11a73db503d1273d860",
    "android_ad_id": "600c8c48-afca-42b8-89e5-4612c086c3cc",
    "idfa": "",
    "idfv": "",
    "openudid": "openudid",
    "language": "zh",
    "os_type": "android",
    "os_version": "7.4.1",
    "screen": {
      "width": 123,
      "height": 234,
      "dpi": 2,
      "pxratio": 34567
    },
    "geo": {
      "lat": 34.567,
      "lon": 107.67,
      "horizontal_accu": 45,
      "vertical_accu": 56
    }
  },
  "user": {
    "id": "34ddd",
    "gender": 0,
    "age": 34,
    "keywords": ["45", "56", "abd"]
  },
  "ads": [
    {
      "unit_type": 3,
      "ad_unit_id": "BB8452AD-06E7-140B-00DC-FD6CB6B40FAA",
      "native": {
        "assets": [
          {
            "id": 1,
            "required": 0,
            "title": {
              "len": 5
            }
          },
          {
            "id": 2,
            "required": 1,
            "image": {
              "type": 3,
              "width": 345,
              "height": 234
            }
          },
          {
            "id": 3,
            "required": 1,
            "data": {
              "type": 2,
              "len": 34
            }
          }
        ]
      }
    }
  ]
}
```

##### 返回示例

```json
{
  "result": 0,
  "msg": "",
  "ads": [
    {
      "id": "476FC7D0-C133-42F5-ED04-20F8C2BF5882",
      "ad_unit_id": "BB8452AD-06E7-140B-00DC-FD6CB6B40FAA",
      "msg": "9D7833A2-B939-16F0-A36C-C4F06518B8A0",
      "app_bundle": "0",
      "target_url": "https://play.google.com/store/apps/details?id=com.zplay.beatracer",
      "target_url_type": 6,
      "playable_ads_html": "<!DOCTYPE html>\n<html>\n  <head>\n    <meta name=\"viewport\" content=\"user-scalable=no, width=device-width, initial-scale=1, maximum-scale=1\">\n    <title>Atmosplayer</title>\n    <meta charset=\"utf-8\"/>\n    <script>\n      window.gestures = [\n  [\n    {\n      \"id\": 0,\n      \"type\": \"swipe\",\n      \"attack\": 1,\n      \"loopStart\": 551,\n      \"target\": 6651,\n      \"fullscreen\": true,\n      \"shapes\": [\n        {\n          \"type\": \"circle\",\n          \"x\": 0.42328042328042326,\n          \"y\": 0.23809523809523808,\n          \"radius\": 0.08465608465608465\n        }\n      ],\n      \"mandatory\": true,\n      \"swipeDirection\": \"LEFT\",\n      \"loop\": true\n    }\n  ],\n  [\n    {\n      \"id\": 1,\n      \"type\": \"swipe\",\n      \"attack\": 9049,\n      \"loopStart\": 9499,\n      \"target\": 14449,\n      \"fullscreen\": true,\n      \"shapes\": [\n        {\n          \"type\": \"circle\",\n          \"x\": 0.42328042328042326,\n          \"y\": 0.23809523809523808,\n          \"radius\": 0.08465608465608465\n        }\n      ],\n      \"mandatory\": true,\n      \"swipeDirection\": \"RIGHT\",\n      \"loop\": true\n    }\n  ],\n  [\n    {\n      \"id\": 2,\n      \"type\": \"swipe\",\n      \"attack\": 18060,\n      \"loopStart\": 18710,\n      \"target\": 23860,\n      \"fullscreen\": true,\n      \"shapes\": [\n        {\n          \"type\": \"circle\",\n          \"x\": 0.42328042328042326,\n          \"y\": 0.23809523809523808,\n          \"radius\": 0.08465608465608465\n        }\n      ],\n      \"mandatory\": true,\n      \"swipeDirection\": \"UP\",\n      \"loop\": true\n    }\n  ],\n  [\n    {\n      \"id\": 3,\n      \"type\": \"swipe\",\n      \"attack\": 28738,\n      \"loopStart\": 30288,\n      \"target\": 35036,\n      \"fullscreen\": true,\n      \"shapes\": [\n        {\n          \"type\": \"circle\",\n          \"x\": 0.42328042328042326,\n          \"y\": 0.23809523809523808,\n          \"radius\": 0.08465608465608465\n        }\n      ],\n      \"mandatory\": true,\n      \"swipeDirection\": \"DOWN\",\n      \"loop\": true\n    }\n  ],\n  [\n    {\n      \"id\": 4,\n      \"type\": \"tap\",\n      \"attack\": 38506,\n      \"target\": 40100,\n      \"fullscreen\": true,\n      \"shapes\": [\n        {\n          \"type\": \"circle\",\n          \"x\": 0.42328042328042326,\n          \"y\": 0.23809523809523808,\n          \"radius\": 0.08465608465608465\n        }\n      ],\n      \"mandatory\": false,\n      \"tapDirection\": 1,\n      \"tapCount\": 1\n    }\n  ]\n];\n      window.showUserGuide = false;\n      window.userGuideUrl = 'undefined';\n      window.userGuidePosition = {};\n      window.installAttributes = {\"x\":0.2779827900049644,\"y\":0.04047619047619048,\"width\":0.49487009763362566,\"percentage\":true};\n      window.showFloatingMenu = true;\n      window.videoOrientation = 0;\n      window.disableUserFeedback = false;\n\n      window.hasEndCard = false;\n      window.endCardSettings = undefined;\n      \n      \n    </script>\n  </head>\n  <body>\n    <div id=\"mainContainer\">\n      <img id=\"loadingImage\" src=\"https://adcdn.zplayads.com/assets/prod/63479990-3d68-11e8-a313-55140a049e95/load.jpg\" />\n      <div id=\"rotatedContainer\">\n\n        <img id=\"closeButton\" src=\"https://adcdn.zplayads.com/assets/images/x_button.png\"/>\n        <img id=\"restartButton\" src=\"https://adcdn.zplayads.com/assets/images/restart.png\"/>\n\n        <img id=\"installButton\" src=\"https://adcdn.zplayads.com/assets/prod/63479990-3d68-11e8-a313-55140a049e95/downloadImage.png?key=641\" />\n\n        <video id=\"atmosPlayer\" webkit-playsinline playsinline muted preload=\"auto\" src=\"https://adcdn.zplayads.com/assets/prod/63479990-3d68-11e8-a313-55140a049e95/transcoded_video_1500kbps.mp4\" poster=\"https://adcdn.zplayads.com/assets/prod/63479990-3d68-11e8-a313-55140a049e95/load.jpg\" autoplay></video>\n        <audio id=\"bgMusicPlayer\" src=\"https://adcdn.zplayads.com/assets/prod/63479990-3d68-11e8-a313-55140a049e95/bgMusic.mp3?key=284\" type=\"audio/mpeg\" loop></audio>\n\n        <video id=\"atmosPlayerEndCard\" webkit-playsinline playsinline muted preload=\"auto\" src=\"\" poster=\"https://adcdn.zplayads.com/assets/prod/63479990-3d68-11e8-a313-55140a049e95/load.jpg\" style=\"z-index: -10;\"></video>\n\n        <canvas id=\"gestureDetector\"></canvas>\n        <canvas id=\"userFeedback\"></canvas>\n\n        <div id=\"floatingMenu\" class=\"simple\">\n          <span class=\"title\">¿ÉÍæµÄÃÔÄãÓÎÏ·</span><img alt=\"gamebox\" class=\"logo\" src=\"https://adcdn.zplayads.com/assets/images/zplayads_logo.png\"/>\n        </div>\n\n      </div>\n    </div>\n    \n    <script src=\"https://adcdn.zplayads.com/engine/prod/3.0.0/atmos.min.js\"></script>\n    \n  </body>\n</html>",
      "price": 30000000,
      "native": {
        "imp_tracker": [
          "https://pa-engine.zplayads.com/v1/tracking?ab_test_id=A011A3BB-9316-08D6-06DD-3DADFA6B73C1&ab_test_object_group_id=default&ad_id=476FC7D0-C133-42F5-ED04-20F8C2BF5882&ad_unit_id=BB8452AD-06E7-140B-00DC-FD6CB6B40FAA&app_id=5C5419C7-A2DE-88BC-A311-C3E7A646F6AF&brand=&bundle_id=bundle_id&channel_id=&channel_share_rate=0&client_id=73AB1CDF-009E-130C-4A15-94901D3470DE&creatives_id=9D7833A2-B939-16F0-A36C-C4F06518B8A0&developer_share_rate=70&device_model=COL-AL10&device_type=phone&engine_events=&industry_id=&last_status=0&network_connection_type=wifi&order_id=94799B85-ED77-B6B5-37B2-2EBCC327131E&os=Android&os_version=7.4.1&pay_by=cpi&pay_event=install&predictive_cpm_cipher=a1ab3e958035bb00b4f5beb2&predictive_cpm_usd_cipher=&promotion_app_id=DF8DD39A-F5B2-A311-BCFE-C6E3CFB75E76&request_id=bfhtamvhefb0iduf5elg&settlement_price_cny=0&settlement_price_usd=0&tracking_type=native_present&unit_price_cny=2000000&unit_price_usd=287166"
        ],
        "assets": [
          {
            "id": 1,
            "title": {
              "text": "Beat Racer"
            },
            "image": {},
            "data": {}
          },
          {
            "id": 2,
            "required": 1,
            "title": {},
            "image": {
              "width": 1280,
              "height": 720,
              "url": "https://pa-cloud.zplayads.com/alfred/static/2018/09/29/5baefb352c87e.jpg"
            },
            "data": {}
          },
          {
            "id": 3,
            "required": 1,
            "title": {},
            "image": {},
            "data": {
              "label": "2",
              "value": "Explore the world by following the trail of alluring beats!"
            }
          }
        ],
        "link": {
          "app_bundle": "0",
          "click_tracker": [
            "https://pa-engine.zplayads.com/v1/tracking?ab_test_id=A011A3BB-9316-08D6-06DD-3DADFA6B73C1&ab_test_object_group_id=default&ad_id=476FC7D0-C133-42F5-ED04-20F8C2BF5882&ad_unit_id=BB8452AD-06E7-140B-00DC-FD6CB6B40FAA&app_id=5C5419C7-A2DE-88BC-A311-C3E7A646F6AF&brand=&bundle_id=bundle_id&channel_id=&channel_share_rate=0&client_id=73AB1CDF-009E-130C-4A15-94901D3470DE&creatives_id=9D7833A2-B939-16F0-A36C-C4F06518B8A0&developer_share_rate=70&device_model=COL-AL10&device_type=phone&engine_events=&industry_id=&last_status=0&network_connection_type=wifi&order_id=94799B85-ED77-B6B5-37B2-2EBCC327131E&os=Android&os_version=7.4.1&pay_by=cpi&pay_event=install&predictive_cpm_cipher=a1ab3e958035bb00b4f5beb2&predictive_cpm_usd_cipher=&promotion_app_id=DF8DD39A-F5B2-A311-BCFE-C6E3CFB75E76&request_id=bfhtamvhefb0iduf5elg&settlement_price_cny=0&settlement_price_usd=0&tracking_type=click_from_native_button&unit_price_cny=2000000&unit_price_usd=287166",
            "https://app.appsflyer.com/com.zplay.beatracer?pid=zplayads&c=playable1"
          ],
          "target_url": "https://play.google.com/store/apps/details?id=com.zplay.beatracer",
          "target_url_type": 6
        }
      }
    }
  ],
  "cur": "CNY"
}
```

#### 激励视频

##### 请求示例

```json
{
  "version": "1.0",
  "developer_token": "D0C85086-DC66-433E-9304-49EAB171D008",
  "need_https": 1,
  "app": {
    "app_id": "5C5419C7-A2DE-88BC-A311-C3E7A646F6AF",
    "app_name": "app_name",
    "bundle_id": "com.playableads.demo",
    "version": "1.0",
    "cat": "cat"
  },
  "device": {
    "model": "COL-AL10",
    "manufacturer": "HONOR",
    "brand": "HONOR",
    "plmn": "46001",
    "device_type": "phone",
    "adt": 1,
    "connection_type": "wifi",
    "carrier": 3,
    "orientation": 0,
    "mac": "28b92b0dde49cff7190841686960c6bc",
    "imei": "6cd5c276d3f6ce4205dde5b1bf913361",
    "android_id": "adf3b4675742e11a73db503d1273d860",
    "android_ad_id": "600c8c48-afca-42b8-89e5-4612c086c3cc",
    "idfa": "",
    "idfv": "",
    "openudid": "openudid",
    "language": "zh",
    "os_type": "android",
    "os_version": "7.4.1",
    "screen": {
      "width": 123,
      "height": 234,
      "dpi": 2,
      "pxratio": 34567
    },
    "geo": {
      "lat": 34.567,
      "lon": 107.67,
      "horizontal_accu": 45,
      "vertical_accu": 56
    }
  },
  "user": {
    "id": "34ddd",
    "gender": 0,
    "age": 34,
    "keywords": ["45", "56", "abd"]
  },
  "ads": [
    {
      "unit_type": 4,
      "ad_unit_id": "3FBEFA05-3A8B-2122-24C7-A87D0BC9FEEC"
    }
  ]
}
```

##### 返回示例

```json
{
  "result": 0,
  "msg": "",
  "ads": [
    {
      "id": "476FC7D0-C133-42F5-ED04-20F8C2BF5882",
      "ad_unit_id": "3FBEFA05-3A8B-2122-24C7-A87D0BC9FEEC",
      "msg": "9D7833A2-B939-16F0-A36C-C4F06518B8A0",
      "app_bundle": "0",
      "target_url": "https://play.google.com/store/apps/details?id=com.zplay.beatracer",
      "target_url_type": 6,
      "playable_ads_html": "<!DOCTYPE html>\n<html>\n  <head>\n    <meta name=\"viewport\" content=\"user-scalable=no, width=device-width, initial-scale=1, maximum-scale=1\">\n    <title>Atmosplayer</title>\n    <meta charset=\"utf-8\"/>\n    <script>\n      window.gestures = [\n  [\n    {\n      \"id\": 0,\n      \"type\": \"swipe\",\n      \"attack\": 1,\n      \"loopStart\": 551,\n      \"target\": 6651,\n      \"fullscreen\": true,\n      \"shapes\": [\n        {\n          \"type\": \"circle\",\n          \"x\": 0.42328042328042326,\n          \"y\": 0.23809523809523808,\n          \"radius\": 0.08465608465608465\n        }\n      ],\n      \"mandatory\": true,\n      \"swipeDirection\": \"LEFT\",\n      \"loop\": true\n    }\n  ],\n  [\n    {\n      \"id\": 1,\n      \"type\": \"swipe\",\n      \"attack\": 9049,\n      \"loopStart\": 9499,\n      \"target\": 14449,\n      \"fullscreen\": true,\n      \"shapes\": [\n        {\n          \"type\": \"circle\",\n          \"x\": 0.42328042328042326,\n          \"y\": 0.23809523809523808,\n          \"radius\": 0.08465608465608465\n        }\n      ],\n      \"mandatory\": true,\n      \"swipeDirection\": \"RIGHT\",\n      \"loop\": true\n    }\n  ],\n  [\n    {\n      \"id\": 2,\n      \"type\": \"swipe\",\n      \"attack\": 18060,\n      \"loopStart\": 18710,\n      \"target\": 23860,\n      \"fullscreen\": true,\n      \"shapes\": [\n        {\n          \"type\": \"circle\",\n          \"x\": 0.42328042328042326,\n          \"y\": 0.23809523809523808,\n          \"radius\": 0.08465608465608465\n        }\n      ],\n      \"mandatory\": true,\n      \"swipeDirection\": \"UP\",\n      \"loop\": true\n    }\n  ],\n  [\n    {\n      \"id\": 3,\n      \"type\": \"swipe\",\n      \"attack\": 28738,\n      \"loopStart\": 30288,\n      \"target\": 35036,\n      \"fullscreen\": true,\n      \"shapes\": [\n        {\n          \"type\": \"circle\",\n          \"x\": 0.42328042328042326,\n          \"y\": 0.23809523809523808,\n          \"radius\": 0.08465608465608465\n        }\n      ],\n      \"mandatory\": true,\n      \"swipeDirection\": \"DOWN\",\n      \"loop\": true\n    }\n  ],\n  [\n    {\n      \"id\": 4,\n      \"type\": \"tap\",\n      \"attack\": 38506,\n      \"target\": 40100,\n      \"fullscreen\": true,\n      \"shapes\": [\n        {\n          \"type\": \"circle\",\n          \"x\": 0.42328042328042326,\n          \"y\": 0.23809523809523808,\n          \"radius\": 0.08465608465608465\n        }\n      ],\n      \"mandatory\": false,\n      \"tapDirection\": 1,\n      \"tapCount\": 1\n    }\n  ]\n];\n      window.showUserGuide = false;\n      window.userGuideUrl = 'undefined';\n      window.userGuidePosition = {};\n      window.installAttributes = {\"x\":0.2779827900049644,\"y\":0.04047619047619048,\"width\":0.49487009763362566,\"percentage\":true};\n      window.showFloatingMenu = true;\n      window.videoOrientation = 0;\n      window.disableUserFeedback = false;\n\n      window.hasEndCard = false;\n      window.endCardSettings = undefined;\n      \n      \n    </script>\n  </head>\n  <body>\n    <div id=\"mainContainer\">\n      <img id=\"loadingImage\" src=\"https://adcdn.zplayads.com/assets/prod/63479990-3d68-11e8-a313-55140a049e95/load.jpg\" />\n      <div id=\"rotatedContainer\">\n\n        <img id=\"closeButton\" src=\"https://adcdn.zplayads.com/assets/images/x_button.png\"/>\n        <img id=\"restartButton\" src=\"https://adcdn.zplayads.com/assets/images/restart.png\"/>\n\n        <img id=\"installButton\" src=\"https://adcdn.zplayads.com/assets/prod/63479990-3d68-11e8-a313-55140a049e95/downloadImage.png?key=641\" />\n\n        <video id=\"atmosPlayer\" webkit-playsinline playsinline muted preload=\"auto\" src=\"https://adcdn.zplayads.com/assets/prod/63479990-3d68-11e8-a313-55140a049e95/transcoded_video_1500kbps.mp4\" poster=\"https://adcdn.zplayads.com/assets/prod/63479990-3d68-11e8-a313-55140a049e95/load.jpg\" autoplay></video>\n        <audio id=\"bgMusicPlayer\" src=\"https://adcdn.zplayads.com/assets/prod/63479990-3d68-11e8-a313-55140a049e95/bgMusic.mp3?key=284\" type=\"audio/mpeg\" loop></audio>\n\n        <video id=\"atmosPlayerEndCard\" webkit-playsinline playsinline muted preload=\"auto\" src=\"\" poster=\"https://adcdn.zplayads.com/assets/prod/63479990-3d68-11e8-a313-55140a049e95/load.jpg\" style=\"z-index: -10;\"></video>\n\n        <canvas id=\"gestureDetector\"></canvas>\n        <canvas id=\"userFeedback\"></canvas>\n\n        <div id=\"floatingMenu\" class=\"simple\">\n          <span class=\"title\">¿ÉÍæµÄÃÔÄãÓÎÏ·</span><img alt=\"gamebox\" class=\"logo\" src=\"https://adcdn.zplayads.com/assets/images/zplayads_logo.png\"/>\n        </div>\n\n      </div>\n    </div>\n    \n    <script src=\"https://adcdn.zplayads.com/engine/prod/3.0.0/atmos.min.js\"></script>\n    \n  </body>\n</html>",
      "price": 30000000
    }
  ],
  "cur": "CNY"
}
```
