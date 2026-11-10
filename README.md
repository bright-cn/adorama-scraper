# Adorama 抓取工具

[![Bright Data](https://img.shields.io/badge/Powered%20by-Bright%20Data-FF9A00?style=flat-square)](https://www.bright.cn/) [![爬虫工具 API](https://img.shields.io/badge/Scraper%20API-Available-FF9A00?style=flat-square)](https://www.bright.cn/products/web-scraper/adorama) [![数据集](https://img.shields.io/badge/Dataset-Available-0066CC?style=flat-square)](https://www.bright.cn/products/datasets/adorama) [![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org) [![许可证：MIT](https://img.shields.io/badge/License-MIT-22C55E?style=flat-square)](LICENSE)

[![促销](https://github.com/bright-cn/Awesome-Web-Scraping/raw/main/Proxies%20and%20scrapers%20GitHub%20bonus%20banner%20CN.png)](https://www.bright.cn/products/web-scraper/adorama)

> **由 [Bright Data](https://www.bright.cn/) 提供支持的 Adorama 数据。**

此代码库提供两种大规模访问 Adorama 数据的方法：

- **[方法 1：Bright Data Adorama 爬虫工具 API](#方法-1bright-data-adorama-爬虫工具-api)**（推荐）- 完全托管的企业级爬虫 API，可自动处理代理、CAPTCHA 和扩展。
- **[方法 2：Bright Data Adorama 数据集](#方法-2bright-data-adorama-数据集)** - 可直接下载的预采集 Adorama 数据集，无需抓取。

## 目录

- [为什么使用 Bright Data 抓取 Adorama？](#为什么使用-bright-data-抓取-adorama)
- [方法 1：Bright Data Adorama 爬虫工具 API](#方法-1bright-data-adorama-爬虫工具-api)
  - [开始使用](#开始使用-adorama-爬虫工具-api)
  - [1. Adorama 数据](#1-adorama-数据)
- [方法 2：Bright Data Adorama 数据集](#方法-2bright-data-adorama-数据集)
- [数据采集方式](#数据采集方式)

## 为什么使用 Bright Data 抓取 Adorama？

抓取 Adorama 面临多项挑战：

- 速率限制：Adorama 会监控请求频率，并可能封禁超出限制的 IP。
- CAPTCHA 检测：自动访问可能会触发 CAPTCHA 验证。
- 身份验证障碍：部分数据需要登录才能访问，且平台会检测自动化访问尝试。
- 动态内容加载：使用简单的 HTTP 请求很难抓取由 JavaScript 渲染的内容。
- IP 封禁：从同一 IP 重复发送请求可能会导致封禁。

Bright Data 的 Adorama 爬虫工具 API 通过以下功能解决这些问题：

- ✅ **内置动态代理**：自动绕过基于 IP 的速率限制
- ✅ **验证码破解**：无需任何额外设置即可应对机器人检测
- ✅ **结构化数据输出**：接收可直接用于分析的整洁 JSON 数据
- ✅ **无需基础设施**：支持任意规模的云端托管抓取
- ✅ **99.9% 正常运行时间 SLA**：为业务关键型工作流提供可靠的数据采集

## 方法 1：Bright Data Adorama 爬虫工具 API

[Bright Data Adorama 爬虫工具 API](https://www.bright.cn/products/web-scraper/adorama) 是一种完全托管的解决方案，无需设置任何基础设施。

### 开始使用 Adorama 爬虫工具 API

1. **注册**一个[免费的 Bright Data 账户](https://www.bright.cn/)
2. **前往** [Adorama 爬虫工具 API](https://www.bright.cn/products/web-scraper/adorama)
3. **从控制面板获取你的 API 令牌**
4. **安装** `requests` 库：`pip install requests`
5. **运行** `adorama_scraper_api_codes/` 中的任意脚本

### 1. Adorama 数据

从 Adorama 采集数据。

#### 输入参数

| 字段 | 类型 | 必填 | 说明 |
|-------|------|----------|-------------|
| `url` | 字符串 | 是 | 要抓取的 Adorama 商品 URL |
| `limit` | 整数 | 否 | 返回结果的最大数量 |
| `include_errors` | 布尔值 | 否 | 在响应中包含错误详情 |
| `notify` | URL | 否 | 采集完成时用于接收通知的 Webhook URL |
| `format` | 枚举 | 否 | 输出格式：`JSON`、`NDJSON`、`JSON Lines`、`CSV` |

#### 响应示例

```json
{
  "additional_image_urls": [
    "https://www.adorama.com/images/Large/ICA5DM4AM.JPG",
    "https://www.adorama.com/images/Large/ICA5DM4.JPG",
    "https://www.adorama.com/images/Large/PROSPCA5DM4.JPG",
    "https://www.adorama.com/images/Large/CSBOEM30A.JPG",
    "https://www.adorama.com/images/Large/GBSMWS10_1.JPG",
    "https://www.adorama.com/images/Large/GXCR10_1.JPG"
  ],
  "availability": "in_stock",
  "brand": "Canon",
  "category_tree": [
    {
      "name": "Adorama",
      "url": "https://www.adorama.com/"
    },
    {
      "name": "Photography",
      "url": "https://www.adorama.com/l/Photography"
    },
    {
      "name": "Cameras",
      "url": "https://www.adorama.com/l/Photography/Cameras"
    },
    {
      "name": "Digital SLR Cameras",
      "url": "https://www.adorama.com/l/Photography/Cameras/Digital-SLR-Cameras"
    },
    {
      "name": "Canon Digital SLR Cameras",
      "url": "https://www.adorama.com/l/Photography/Cameras/Canon~Digital-SLR-Cameras"
    }
  ],
  "category_urls": [
    "https://www.adorama.com/",
    "https://www.adorama.com/l/Photography",
    "https://www.adorama.com/l/Photography/Cameras",
    "https://www.adorama.com/l/Photography/Cameras/Digital-SLR-Cameras",
    "https://www.adorama.com/l/Photography/Cameras/Canon~Digital-SLR-Cameras"
  ],
  "description": "The EOS 5D Mark IV camera builds on the powerful legacy of the 5D series, offering amazing refinements in image quality, performance and versatility. Canon\u0027s commitment to imaging excellence is the soul of the EOS 5D Mark IV. Wedding and portrait photographers, nature and landscape shooters, as well as creative videographers will appreciate the brilliance and power that the EOS 5D Mark IV delivers. Superb image quality is achieved with Canon\u0027s all-new 30.4 Megapixel full-frame sensor, and highly-detailed 4K video is captured with ease. Focus accuracy has been improved with a refined 61-point AF system and Canon\u0027s revolutionary Dual Pixel CMOS AF for quick, smooth AF for both video and Live View shooting. Fast operation is enhanced with Canon\u0027s DIGIC 6+ Image Processor, which provides continuous shooting at up to 7.0 fps. Built-in Wi-Fi, GPS and an easy-to-navigate touch-panel LCD allow the camera to become an extension of you. When quality matters, the EOS 5D Mark IV helps deliver results to inspire even the most discerning imagemaker. 30.4 Megapixel Full-frame CMOS Sensor The EOS 5D Mark IV camera boasts a full-frame, high-speed CMOS sensor that\u0027s ideal for a broad range of applications with its remarkable high-resolution abilities. Measuring approximately 36.0mm x 24.0mm, the same size and ratio as a 35mm film frame, it records 30.4 effective Megapixels at normal ISOs of up to 32000. It also captures incredible still and 4K video clips suitable for significant post-processing, retouching and cropping. Versatile in virtually all kinds of light and any shooting situation from print and wedding to full-bleed magazine spreads and other commercial or fine art use, the EOS 5D Mark IV consistently produces high-resolution 4K video and image files that are easily compatible with any number of diverse workflows. ISO 100-32000 (expandable to 50-102400) Featuring an ISO range of 100-32000 (expandable to 50-102400), the EOS 5D Mark IV camera is incredibly well-suited for low-light photography. Its sensor has an improved S/N ratio plus an improved noise-processing algorithm to help deliver high-level light sensitivity along with its high resolution, with virtually no compromise in image quality. Whether working in a dimly lit auditorium, trying to capture the action at night, photographing at the fastest possible shutter speed or simply suppressing camera shake blur, the EOS 5D Mark IV has an extended ISO range that contributes to its ability to excel in nearly every situation it faces. 4K Motion JPEG video (DCI cinema-type 4096 x 2160) at 30p or 24p; in-camera still frame grab of 4K 8.8-Megapixel images; multiple video options include Full HD up to 60p, and HD up to 120p. The EOS 5D Mark IV is a remarkably capable video camera. Thanks to its impressive CMOS sensor and its high-speed DIGIC 6+ Image Processor, it can transition from taking still photographs to shooting videos in a near instant, capturing Digital Cinema (DCI) standard 4K (Motion JPEG) videos of 4096 x 2160 pixels at up to 30 or 24 fps. Adding to its versatility, it also supports the 4K broadcasting standard of 3840 x 2160 pixels with slight trimming on the left and right sides. Superb Dual Pixel CMOS AF for responsive and smooth AF during video or Live View shooting; LCD monitor has full touch-screen interface, including selection of AF area. Adding to its powerful and portable design, the EOS 5D Mark IV camera utilizes Canon\u0027s smooth, fast and intelligent Dual Pixel CMOS AF. Featuring two photodiodes per pixel and each pixel capable of phase-difference detection autofocus, the CMOS sensor can deliver fast and accurate AF throughout approximately 80% of the image plane. Able to detect shifts in movement at the pixel level, Dual Pixel CMOS AF enables continuous automatic AF and AF tracking that enhances overall camera operation for sharp still images and smooth, accurate focus transitions in movies. Dual Pixel CMOS AF Adding to its powerful and portable design, the EOS 5D Mark IV camera utilizes Canon\u0027s smooth, fast and intelligent Dual Pixel CMOS AF. Featuring two photodiodes per pixel and each pixel capable of phase-difference detection autofocus, the CMOS sensor can deliver fast and accurate AF throughout approximately 80% of the image plane. Able to detect shifts in movement at the pixel level, Dual Pixel CMOS AF enables continuous automatic AF and AF tracking that enhances overall camera operation for sharp still images and smooth, accurate focus transitions in movies. Working with the EOS 5D Mark IV\u0027s 3.2\" touch panel LCD screen, Dual Pixel CMOS AF lets photographers select focus points throughout the frame with the touch of a finger, and confirm focus by zooming in on the image or enlarging stills grabbed from video recordings. 3.2\" Touch Panel LCD The EOS 5D Mark IV camera features a 1.62 million dot, low-reflection 3.2-inch Clear View LCD II monitor for bright, sharp display in a wide variety of shooting situations. The LCD\u0027s touch panel surface facilitates fast, intuitive operation, including AF frame switching, menu and setting changes plus image magnification during Live View shooting and movie shooting. Still photographs can also be captured quickly with the touch panel\u0027s shutter release function. A customizable Quick Control screen adds flexibility and convenience for specific users\u0027 preferences. Image review and playback are also enhanced with the EOS 5D Mark IV camera\u0027s Clear View LCD II Monitor. Not only does the EOS 5D Mark IV\u0027s LCD provide a high-precision image for composition and playback, but it also remains visible even when the photographer is wearing polarized sunglasses! In numerous situations in the studio and in the field, the EOS 5D Mark IV\u0027s LCD panel is an ideal complement to its amazing TTL viewfinder. Includes EOS 5D Mark IV Body, Eyecup Eg, Wide Neck Strap EW-EOS5DMK IV, USB Interface Cable IFC-150U II, Battery Charger LC-E6, Battery Pack LP-E6N, Cable Protector, EOS Digital Solution Disc, Camera Instruction Manual",
  "group_id": "ICA5DM4AM",
  "image_url": "https://www.adorama.com/images/Large/canon-eos-5d-mark-iv-dslr_ica5dm4am.webp",
  "item_id": "ICA5DM4AM",
  "listing_has_variations": true,
  "price": "$2,499.00",
  "product_category": "Adorama \u003e Photography \u003e Cameras \u003e Digital SLR Cameras \u003e Canon Digital SLR Cameras",
  "return_policy": "https://www.adorama.com/help/returnPolicy",
  "return_window": 30,
  "review_count": 822,
  "reviews": [
    {
      "content": "I purchased this camera body to use as a second camera for use in the field to be able to quickly switch between my long lens and my medium range zoom. To be clear, both of my camera bodies are now the EOS 5D Mark 4 and my selection of getting a second identical one is based on my experience with the first. This is a great camera!!",
      "max_rating": 5,
      "min_rating": 1,
      "rating": 5,
      "review_id": "1954520",
      "title": "Outstanding high resolution DSLR"
    },
    {
      "content": "I was frustrated to use the app version GPS with my Leica LUMIX and Other cameras, despite having many cameras of all made I regret selling my MK4 years go and bought 2 in 2026! Because nothing can replace it at this price! I have other Canon R5C, R5, 5DSR,  LUMIX, Leica, Sony, Fujifilm and none have built in GPS a much needed feature for landscape , travel and street photography   My other options were to spent $4500 on R3 or $5500 or Nikon z9. I decided that 5DMK4 is the best option for me I have the Ef lenses and it\u0027s also a better option than all my mirrorless cameras do4 strobe and flash photography. Thank you Adorama for a great experience!",
      "max_rating": 5,
      "min_rating": 1,
      "rating": 5,
      "review_id": "1952154",
      "title": "Yes it\u0027s still relevant in 2026! Best landscape, street \u0026 travel Pro cam with built in GPSat this price range!"
    },
    {
      "content": "Purchased the 5D Mk 4 body because it will be the last of 5D series. Have 2 already and they are truly great work horses!  Easier to work with and more dependable then the mirrorless models!",
      "max_rating": 5,
      "min_rating": 1,
      "rating": 5,
      "review_id": "1950187",
      "title": "EOS 5D Mark IV Body"
    },
    {
      "content": "I bought this camera a little over a year ago and I love it. This camera is a tank. I love the sound of the shutter.  The pictures are immaculate and I can crop with no pixels. It feels great in the hand, its weight helps keep the shot steady. The view finder is bright and a real life view. No lag. I hate electric viewfinders. They are terrible. I have a mirrorless camera and can\u0027t stand the delay when I pull it up to my eyes. There is an ocean of lenses available for this. I know mirror-less is the direction many manufacturers are going. I hope Canon continues to make DSLR alternative as time goes on.  It\u0027s a great camera if you\u0027re on the fence. If you\u0027re not shooting video this will suit you. I shoot a on of film as well.  I own A EOS 1n \u0026 EOS 3.  All great cameras and it\u0027s great to have lenses that work across the board. I wish Canon would have made RF backwards compatible. That would\u0027ve been fun.",
      "max_rating": 5,
      "min_rating": 1,
      "rating": 5,
      "review_id": "1918943",
      "title": "Still an amazing camera"
    },
    {
      "content": "Fast shipping on a great camera. This is my second body in this model after using my original for several years.",
      "max_rating": 5,
      "min_rating": 1,
      "rating": 5,
      "review_id": "1806050",
      "title": "Canon 5d mark iv"
    },
    {
      "content": "During the Spring of this year, 2024, I bought a new EOS 5D Mark IV from Camera Mall in Ann Arbor, MI. I went on line and saw they had them in stock, so I paid for it in advance and then jumped in my car and drove over 55 miles to pick it up. The thought of owning this camera body was exciting because I\u0027d read so many good things about it, especially since earlier this year in March, I met a professional that was shooting with a 1D. I told him my best camera is a Canon 6D and wondered if the 5D Mark IV was significantly better. He animately said yes! and that I would notice a major difference. After this statement and having read other reviews, I was game to take a chance, especially since I\u0027m not not interested in switching to mirrorless, not even with an adapter. Besides, that\u0027s what a cell phone\u0027s set up is, right? Plus, I own a Canon SX40 HS bridge camera and a Ricoh-Pentax WG-4 pocket camera. Neither are DSLR but I\u0027m good with those and would rather concentrate on the old mirror DSLR community of photography.\u003cbr /\u003eWell, I must say I\u0027ve had nothing but good things and experiences with this apparatus, even though I paid $500.00 more than the advertised current sale price. My evaluative opinion may not be the best; I consider myself a novice professional. For me, it\u0027s just an addictive hobby but I have been paid for my photography (unsolicited) and some of my pictures have been featured in a newspaper. I\u0027ve paired my shooting with 5 different Canon L lenses and based off of other reviews I\u0027ve read here on the Canon website, I may be adding the EF 24-70 2.8 L to my lens collection. \u003cbr /\u003eSo far, I\u0027d say this body has performed well and I\u0027m glad I bought it while the getting is not as good as the RF mirrorless mounts. \u003cbr /\u003eMy two thumbs say Yes! This camera is well worth the ownership!",
      "max_rating": 5,
      "min_rating": 1,
      "rating": 5,
      "review_id": "1809139",
      "title": "My Two Thumbs Say...."
    },
    {
      "content": "Even this camera model is over a decade old but still one of great camera out there!!!  Some people reported blurry pictures... well, if you do not know how to take good pictures with the advanced settings, just stick to your smartphones and DSLR/Mirrorless sophisticated equipments are not for you. Need intelligence and skill to use beyond Auto Mode.",
      "max_rating": 5,
      "min_rating": 1,
      "rating": 5,
      "review_id": "1770338",
      "title": "Great camera!"
    },
    {
      "content": "Purchased and tried for 7 days.  Tried every setting I could find and could not take crisp sharp photos.  Used tripod and shutter release.  Contacted Canon, no help.  I suspect the low pass filter is the culprit.  Returned camera.  Disappointed with Canon.  Have EOS 5D Mark III and am very pleased.",
      "max_rating": 5,
      "min_rating": 1,
      "rating": 2,
      "review_id": "1753322",
      "title": "Blurry pictures."
    },
    {
      "content": "Very nice camera. Upgrade from my mark II. Would definitely recommend",
      "max_rating": 5,
      "min_rating": 1,
      "rating": 5,
      "review_id": "1977851",
      "title": "Retired"
    },
    {
      "content": "After three years of use, this camera continues to provide a lot of features that make it rank first among my Canon cameras. It has no substitute.",
      "max_rating": 5,
      "min_rating": 1,
      "rating": 5,
      "review_id": "1697277",
      "title": "Best camera ever."
    }
  ],
  "sale_price": "$1,999.00",
  "seller_privacy_policy": "https://www.adorama.com/help/privacy",
  "seller_tos": "https://www.adorama.com/help/termsAndConditions",
  "seller_url": "https://www.adorama.com/",
  "star_rating": 5,
  "store_country": "US",
  "store_name": "Adorama",
  "target_countries": [
    "US"
  ],
  "title": "Canon EOS 5D Mark IV Digital SLR Camera USA Warranty - Bundle with 64GB U3 SDHC Card, Holster Case, Table Top Tripod, Cleaning Kit, Memory Wallet, Screen Protector, Card Reader, Mac Software Package",
  "url": "https://www.adorama.com/canon-eos-5d-mark-iv-digital-slr-camera-body-bundle-64gb/p/ica5dm4am",
  "variant_attributes": [
    {
      "name": "Lens Included",
      "value": "Without Lens"
    },
    {
      "name": "Edition",
      "value": "Standard"
    },
    {
      "name": "Kit Style",
      "value": "Included Value"
    }
  ],
  "variant_id": "ICA5DM4AM",
  "variants": [
    {
      "variant_options": [
        {
          "image": "https://www.adorama.com/images/Large/ICA5DM4AM.JPG",
          "in_stock": true,
          "option_id": "ICA5DM4AM",
          "option_name": "Without Lens",
          "option_price": 1999
        },
        {
          "image": "https://www.adorama.com/images/Large/ICA5DM4KA.JPG",
          "in_stock": true,
          "option_id": "ICA5DM4KA",
          "option_name": "24-105mm",
          "option_price": 3199
        }
      ],
      "variant_type": "Lens Included"
    },
    {
      "variant_options": [
        {
          "image": "https://www.adorama.com/images/Large/ICA5DM4AM.JPG",
          "in_stock": true,
          "option_id": "ICA5DM4AM",
          "option_name": "Standard",
          "option_price": 1999
        },
        {
          "image": "https://www.adorama.com/images/Large/ICA5DM4LA.JPG",
          "in_stock": true,
          "option_id": "ICA5DM4LA",
          "option_name": "Canon Log",
          "option_price": 2599
        }
      ],
      "variant_type": "Edition"
    },
    {
      "variant_options": [
        {
          "image": "https://www.adorama.com/images/Large/ICA5DM4.JPG",
          "in_stock": true,
          "option_id": "ICA5DM4",
          "option_name": "Base",
          "option_price": 1999
        },
        {
          "image": "https://www.adorama.com/images/Large/ICA5DM4AM.JPG",
          "in_stock": true,
          "option_id": "ICA5DM4AM",
          "option_name": "Included Value",
          "option_price": 1999
        },
        {
          "image": "https://www.adorama.com/images/Large/ICA5DM4LBG.JPG",
          "in_stock": false,
          "option_id": "ICA5DM4LBG",
          "option_name": "with Battery Grip",
          "option_price": 2948
        }
      ],
      "variant_type": "Kit Style"
    }
  ]
}
```

👉 查看[完整 Python 代码](adorama_scraper_api_codes/adorama_scraper.py)

## 方法 2：Bright Data Adorama 数据集

如果你需要无需编写任何抓取代码即可使用的数据，[Bright Data Adorama 数据集](https://www.bright.cn/products/datasets/adorama)可提供预先采集并定期更新的数据，支持即时下载。

**为什么选择数据集而不是 API？**

- 📦 **即时访问**：无需设置、无需代码，也无需等待采集
- 🔄 **定期更新**：按照固定计划刷新最新数据
- 📊 **多种格式**：支持下载为 JSON、JSONL 或 CSV
- 🌍 **海量规模**：覆盖 Adorama 所有主要类别的数百万条记录
- ✅ **完全合规**：数据来源符合道德规范，并经过法律合规审查

👉 **[探索 Adorama 数据集](https://www.bright.cn/products/datasets/adorama)**

## 数据采集方式

| 功能 | Bright Data 爬虫工具 API | Bright Data 数据集 |
|---------|------------------------|---------------------|
| 需要设置 | 仅需 API 令牌 | 无需设置 |
| 实时数据 | ✅ 是 | ❌ 预先采集 |
| 自定义查询 | ✅ 完全控制 | ❌ 固定模式 |
| 包含代理 | ✅ 内置动态代理 | N/A |
| CAPTCHA 破解 | ✅ 自动 | N/A |
| 规模 | 无限制 | 无限制 |
| 结构化输出 | ✅ JSON / NDJSON / JSON Lines / CSV | ✅ JSON / JSONL / CSV |
| 支持 | 企业级全天候支持 | 企业级全天候支持 |

---

🔗 **了解更多**：[https://www.bright.cn/products/web-scraper/adorama](https://www.bright.cn/products/web-scraper/adorama)
