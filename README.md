#### 产品

名称：小小app

开发者：刘丽冰

简介：一款记录用户心事的树洞型app。

#### 痛点

1、每个人都是一座孤岛，倾诉欲无法得到满足。
 
2、经历的事情和当时的心情很容易忘却。

3、纸质日记不好保存，也无法随时携带。

#### 目标



#### 加值宣言

小树洞模块-使用语音识别api:小树洞如同一个用户可以倾诉的对象，用户可以选择语音输入，也可以选择文字输入，形成一篇小日记；
小心情模块-使用自然语言处理的情感分析api：根据用户的小日记，分析用户心情，标记用户心情，并形成心情曲线。

#### 核心价值



#### 核心价值与用户痛点

#### 需求列表

| 需求                         | 重要程度 | 可用api           |实现可能性|
| ---------------------------- | -------- | ----------------- | ----------------- |
| 倾听、记录心事               | ⭐⭐⭐⭐   | 语音识别 |高|
| 分析、记录心情         | ⭐⭐⭐⭐      | 自然语言处理-情感分析 |高|
| 增加图片，并根据图片分类        | ⭐      | 图像识别 |不做|























#### 产品

名称：好好恰饭小程序

开发者：刘丽冰

简介：一款识别、推荐各种果蔬、菜品的小程序。

#### 痛点：

1、很多年轻人分不清水果蔬菜的名称；

2、选择困难症，永远决定不了要吃什么；


#### 目标：

- 给用户识别各种各样的果蔬和菜品，去超市和菜市场购买水果蔬菜的时候可以拍照识别出水果蔬菜的名称，并结合用户识别记录，推荐适合用户的果蔬菜品。

#### 加值宣言

水果蔬菜的种类丰富，还有些相似的难以辨别，再加上很多年轻人的常识和生活经验不足，可能无法识别一些水果或蔬菜的名称，小程序有果蔬识别、菜品识别、推荐三个功能，其中用图像识别api中的果蔬识别和菜品识别,帮助用户识别不同的果蔬、菜品，帮助对果蔬等不熟悉的年轻用户辨别各种果蔬、菜品；结合用户识别的记录和用户自行填入的口味喜好，推荐适合用户的果蔬、菜品，拯救选择困难症。

#### 核心价值：

解决用户不认识水果蔬菜、菜品的盲区（最小可用产品），满足用户的认知欲，帮助用户选择购买。

#### 人工智能概率性：

清晰的图片都可以准确识别出来，如果图片过于模糊，则容易判断失误。一般正常拍摄的都可以识别成功。

#### 核心价值与用户痛点：

| 用户痛点                         |核心价值          |
| ---------------------------- |----------------- |
| 年轻人分不清水果蔬菜的名称        |帮助用户识别果蔬、菜品 |
| 饭点必备选择困难症  | 给用户推荐合适的菜品 |

#### 需求列表

| 需求                         | 重要程度 | 可用api           |实现可能性|
| ---------------------------- | -------- | ----------------- | ----------------- |
| 分辨不同的果蔬               | ⭐⭐⭐   | 图像识别-果蔬识别 |高|
| 识别各种菜品         | ⭐⭐⭐      | 图像识别-菜品识别 |高|
| 了解菜品的基本信息和禁忌人群         | ⭐      | 图像识别-菜品识别 |较高|
| 根据心情推荐饮食         | ⭐      | 自然语言处理-情感分析 ||


#### 用户使用场景

| 场景                         | 动作 | 
| ---------------------------- | -------- | 
| 用户去逛菜市场，看到一颗绿色的蔬菜，但不认识  | 用户拿出手机拍下该物识别  |
| 用户在网上看到网友分享的一份菜品图片，但不知道是什么菜     | 用户拿出手机拍下该物识别      | 
| 用户肚子饿了，但决定不了午餐吃什么| 用户点击推荐，小程序根据用户的识别记录推荐菜品|
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

