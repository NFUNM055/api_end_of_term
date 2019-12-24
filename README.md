#### 产品

| 产品名称  |饮食日记app          |
| ---------------------------- |----------------- |
| 产品负责人     |刘丽冰 |
| 状态  | 未完成 |

开发者：刘丽冰

简介：记录你的饮食及日常，从中分析你的情感倾向，根据记录为你推荐饮食。


#### 痛点：

1、选择困难症，永远决定不了要吃什么；

2、不认识/记不住一些果蔬、菜品的名称

3、经常忘记吃饭/忘记之前吃过什么

#### 加值宣言

民以食为天，吃是生活中很小很自然的一件事情，但也是一项很重要的事情，

图像识别-果蔬识别api，
图像识别-菜品识别api
自然语言处理-情感倾向分析

#### 核心价值：



#### 人工智能概率性：


#### 核心价值与用户痛点：

| 用户痛点                         |核心价值          |
| ---------------------------- |----------------- |
| 不认识/记不住一些果蔬、菜品的名称     |帮助用户识别果蔬、菜品 |
| 饭点必备选择困难症  | 给用户推荐合适的菜品 |

#### 需求列表

| 需求                         | 重要程度 | 可用api           |实现可能性|
| ---------------------------- | -------- | ----------------- | ----------------- |
| 一键推荐饮食|⭐⭐⭐ |无需api,从用户饮食日记的记录中提取推荐|
| 识别各种果蔬               | ⭐⭐⭐   | 图像识别-果蔬识别 |高|
| 识别各种菜品         | ⭐⭐⭐      | 图像识别-菜品识别 |高|
| 分析情感倾向         | ⭐⭐      | 自然语言处理-情感分析 |高|
| 了解菜品的基本信息和禁忌人群         | ⭐      | 图像识别-菜品识别 |较高|


#### 原型

#### api调用

##### 百度api

1、果蔬识别——秋葵
```
import requests
import base64

request_url = "https://aip.baidubce.com/rest/2.0/image-classify/v1/classify/ingredient"
f = open("timg.jfif", 'rb')
img = base64.b64encode(f.read())

params = {"image":img}
access_token = '24.2a1c09a400df3dcf3bfe1491bc6ab4e8.2592000.1578035412.282335-17927505'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/x-www-form-urlencoded'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())
```
结果：识别成功
```
{'log_id': 5186393473038834148, 'result_num': 5, 'result': [{'score': 0.6500539779663086, 'name': '黄秋葵'}, {'score': 0.34338581562042236, 'name': '秋葵'}, {'score': 0.0012838267721235752, 'name': '黄瓜'}, {'score': 0.0011446732096374035, 'name': '豌豆'}, {'score': 0.0007779692532494664, 'name': '非果蔬食材'}]}
```

2、果蔬识别——枇杷

结果：识别成功
```
{'log_id': 2907733790495041515, 'result_num': 5, 'result': [{'score': 0.8762322068214417, 'name': '枇杷'}, {'score': 0.12325529754161835, 'name': '枇杷果'}, {'score': 0.0002433160989312455, 'name': '非果蔬食材'}, {'score': 0.00013505088281817734, 'name': '海棠果'}, {'score': 1.188514033856336e-05, 'name': '大南果梨'}]}
```
3、菜品识别——红烧肉
```
import requests
import base64

request_url = "https://aip.baidubce.com/rest/2.0/image-classify/v2/dish"
f = open('hs.jfif', 'rb')
img = base64.b64encode(f.read())

params = {"image":img,"top_num":5,"baike_num":10}
access_token = '24.2a1c09a400df3dcf3bfe1491bc6ab4e8.2592000.1578035412.282335-17927505'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/x-www-form-urlencoded'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())
```
结果——识别成功，且有关于菜品的基本介绍
```
{'log_id': 395180959258989995, 'result_num': 5, 'result': [{'calorie': '227', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E7%BA%A2%E7%83%A7%E8%82%89/571767', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/d62a6059252dd42a65f3ccbf0e3b5bb5c9eab828.jpg', 'description': '红烧肉是一道著名的大众菜肴，属于鲁菜。其以五花肉为制作主料，最好选用肥瘦相间的三层肉(五花肉)来做，做法多达二三十种。红烧肉的烹饪技巧，锅具以砂锅为主，做出来的肉肥瘦相间，香甜松软，入口即化。红烧肉在我国各地流传甚广，具有一定的营养价值。'}, 'probability': '0.669245', 'name': '红烧肉'}, {'calorie': '470', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E7%BA%A2%E7%83%A7%E8%82%89%E9%A5%AD/2626130', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/cdbf6c81800a19d8dbc786ab3dfa828ba71e4653.jpg', 'description': '红烧肉饭是由萝卜干、猪肋条肉配以佐料，拌上米饭后制成的一道主食。猪肉含有丰富蛋白质和氨基酸，大米含有B族维生素还具有补中益气、健脾养胃的功效。本品具有香而不腻，口感绵软的特点。'}, 'probability': '0.105687', 'name': '红烧肉饭'}, {'calorie': '283', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E4%B8%9C%E5%9D%A1%E8%82%98%E5%AD%90/327468', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/060828381f30e92406bdf89540086e061d95f77d.jpg', 'description': '东坡肘子，四川省眉山市特产，国家地理标志产品。东坡肘子具有汤汁乳白，猪肘烂软，肉质细嫩、肉味醇香、有嚼头，肥而不腻等优点。2013年12月，东坡肘子成功获批国家地理标志保护产品称号。'}, 'probability': '0.0486278', 'name': '东坡肘子'}, {'has_calorie': False, 'baike_info': {}, 'probability': '0.0267652', 'name': '肉盖饭'}, {'calorie': '143', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E9%BB%91%E7%8C%AA%E8%82%89/9675905', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/b812c8fcc3cec3fd7e22ad95dc88d43f87942735.jpg', 'description': '黑猪肉肉质细腻且营养价值丰富。肌肉中的不饱和脂肪酸的含量为8.87%，特别是亚麻酸能保护肝脏，能提高人体免疫能力，同时还可以改善人体内SOD的活性，抑制MDA的生成，延缓机体衰老，细胞老化。含量显著高于其他猪种，对人体有极高的营养价值及保健作用，如长期食用可延年益寿，并有着汤汁浓郁，绕齿留香。黑猪肌肉内的肉品鲜味主要特征氨基酸天门冬氨酸、谷氨酸、甘氨酸、丙氨酸和肌苷酸的总含量明显高于洋猪，烹饪调出的汤汁浓郁，口留余香，对人体有着较大的辅助功能。'}, 'probability': '0.0224778', 'name': '黑猪肉'}]}
```

