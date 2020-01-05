#### 产品

| 产品名称  |饮食日记app  |
| -------- |-------- |
| 产品负责人 |刘丽冰 |
| 状态  | 未完成 |

【一句话版本】

简介：“饮食日记”app是一款饮食记录软件，可以帮用户识别果蔬、菜品，同时可以记录、分享自己的的饮食小日记。

【一分钟版本】


#### 痛点：

1、生活中，用户可能会遇到自己不熟悉，甚至完全不认识的果蔬、菜品；

2、网上冲浪时，发现一些果蔬/菜品的图片，但不确定是什么；

3、用户想要吃一款美食，但是担心卡路里太高；

4、心情；

5、用户想要看看他人的饮食生活，找到更多新鲜感和不一样的食物；

6、用户经过努力做了一份非常美味的菜品时，想要记录下来并和别人分享。

#### 加值宣言

图像识别api-果蔬识别：用户通过拍摄/上传本地图片的方式，对水果、蔬菜进行识别，最终识别出水果、蔬菜的名称；
图像识别api-菜品识别：用户通过拍摄/上传本地图片的方式，对菜品进行识别，可以帮助用户辨别各种菜品的名称，并返回卡路里、基本营养成分等一些基本介绍；
自然语言处理api-情感倾向分析：饮食和情感是密不可分的，饮食可以影响情感，情感也会反过来影响饮食。根据用户在饮食日记中编写的文字，分析用户的情感倾向，给日记形成一个情感标签，连续记录一个星期形成情感曲线。

#### 核心价值：

最小可行性产品：识别果蔬、菜品的名称

该app主要分为三个模块【日记】【社区】【我的】，其中【日记】为主要功能。用户可以通过拍照/上传图片的形式，识别果蔬、菜品的图片，不管是生活中吃到的、看到的，还是网上随手存的，都可以在这里识别，如果想要添加到饮食日记中，也可以加上文本内容，形成一个饮食小日记。饮食日记可以识别出果蔬、菜品的名称，以及菜品的相关卡路里等信息，如果希望获得更多的信息则可以通过点击外链到百科百科的信息。

#### 需求列表

| 需求                         | 重要程度 | 可用api           |实现可能性|
| ---------------------------- | -------- | ----------------- | ----------------- |
| 识别各种果蔬的名称               | ⭐⭐⭐   | 图像识别-果蔬识别 |高|
| 识别各种菜品的名称、卡路里        | ⭐⭐⭐      | 图像识别-菜品识别 |高|
| 分析日记文字的情感倾向         | ⭐⭐      | 自然语言处理-情感分析 |较高|
| 了解菜品的更多信息，如营养价值、禁忌人群等         | ⭐  | 图像识别-菜品识别 |一般（不是所有识别的菜品都有这些信息）|


#### 原型




#### 人工智能概率性：


#### api调用

##### 百度api

1、果蔬识别——秋葵
```python
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
```python
{'log_id': 5186393473038834148, 'result_num': 5, 'result': [{'score': 0.6500539779663086, 'name': '黄秋葵'}, {'score': 0.34338581562042236, 'name': '秋葵'}, {'score': 0.0012838267721235752, 'name': '黄瓜'}, {'score': 0.0011446732096374035, 'name': '豌豆'}, {'score': 0.0007779692532494664, 'name': '非果蔬食材'}]}
```

2、果蔬识别——枇杷

结果：识别成功
```python
{'log_id': 2907733790495041515, 'result_num': 5, 'result': [{'score': 0.8762322068214417, 'name': '枇杷'}, {'score': 0.12325529754161835, 'name': '枇杷果'}, {'score': 0.0002433160989312455, 'name': '非果蔬食材'}, {'score': 0.00013505088281817734, 'name': '海棠果'}, {'score': 1.188514033856336e-05, 'name': '大南果梨'}]}
```
3、菜品识别——猪蹄
```python
import requests
import base64

request_url = "https://aip.baidubce.com/rest/2.0/image-classify/v2/dish"
f = open('zt.jpg', 'rb')
img = base64.b64encode(f.read())

params = {"image":img,"top_num":1,"filter_threshold":0.95,"baike_num":7}
access_token = '24.e264db18593145433bf09c4f41a16e54.2592000.1580824242.282335-17927505'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/x-www-form-urlencoded'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())
```
结果——识别成功
```python
{'log_id': 3822699200360737957, 'result_num': 6, 'result': [{'calorie': '260', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E7%8C%AA%E8%B9%84/808853', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/fd039245d688d43f8d6b138c731ed21b0ff43b89.jpg', 'description': '猪蹄，是指猪的脚部(蹄)和小腿，在中国又叫元蹄。在华人世界中，猪蹄是经常被人食用的部位之一，有多种不同的烹调作法。猪蹄含有丰富的胶原蛋白质，脂肪含量也比肥肉低。它能防治皮肤干瘪起皱、增强皮肤弹性和韧性，对延缓衰老和促进儿童生长发育都具有特殊意义。为此，人们把猪蹄称为“美容食品” 和“类似于熊掌的美味佳肴”。挑选猪蹄需注意，颜色发白，个头过大，脚趾处分开并有脱落痕迹的是双氧水浸泡的化学猪蹄。'}, 'probability': '0.989221', 'name': '猪蹄'}, {'calorie': '260', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E7%8C%AA%E8%84%9A%E9%A5%AD/8055995', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/95eef01f3a292df57a026263be315c6035a87387.jpg', 'description': '猪脚饭是广东省惠来县经典的小吃，属于粤菜系。其味道鲜美加以本镇的特色米饭，组合成了隆江猪脚饭。肥而不腻，入口香爽，是当地一道有名的菜肴。经济实惠，方便快捷，爽香开胃，是深得人们喜爱的快餐饮品。猪脚饭，入口软烂无渣、肥而不腻、香气四溢、胶棉而不沾牙，达到了落口消融的境界，肘子丰富的胶质和“蹄筋、骨、肉的的错综复杂”体现得淋漓尽致。'}, 'probability': '0.00218056', 'name': '猪脚饭'}, {'calorie': '124', 'has_calorie': True, 'baike_info': {}, 'probability': '0.00211029', 'name': '猪蹄煲'}, {'calorie': '199', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E7%83%A4%E7%8C%AA%E8%82%98/12989548', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/5882b2b7d0a20cf4897c7cb374094b36adaf99ea.jpg', 'description': '烤猪肘是以猪肘为主材的菜肴名。'}, 'probability': '0.00117759', 'name': '烤猪肘'}, {'calorie': '107', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E7%83%A4%E7%BF%85%E6%A0%B9/10082850', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/b03533fa828ba61efc18b2974f34970a314e5997.jpg', 'description': '烤翅根是一道由翅根，土豆等食材制成的食品。'}, 'probability': '0.000440045', 'name': '烤翅根'}, {'calorie': '223', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E6%8E%92%E9%AA%A8%E7%85%B2/9020367', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/03087bf40ad162d9b05eb76b12dfa9ec8a13cd11.jpg', 'description': '排骨煲的做法详细介绍 菜系及功效： 脾调养食谱 气血双补食谱 胃调养食谱 补虚养身食谱 滋阴食谱 健脾开胃食谱'}, 'probability': '0.000336915', 'name': '排骨煲'}]}
```
4、自然语音处理-情感倾向：
```python
from aip import AipNlp

APP_ID = '18021502'
API_KEY = 'Gp9nWH3HxVt8OAGcyHzXtHTZ'
SECRET_KEY = 'SriOcLgEstfCSy9u5oWR7vrUXpuW8SGQ'

client = AipNlp(APP_ID, API_KEY, SECRET_KEY)
text = "今天天气挺好的，心情也很好，但我说好减肥的，耐不住妈妈煮的鸡煲太好吃了，害我整整吃了两碗饭！"
client.sentimentClassify(text)
```
结果：积极指数：0.98，消极指数：0.02，偏正向情绪。
```python
{'log_id': 2523262217194262296,
 'text': '今天天气挺好的，心情也很好，但我说好减肥的，耐不住妈妈煮的鸡煲太好吃了，害我整整吃了两碗饭！',
 'items': [{'positive_prob': 0.976739,
   'confidence': 0.948309,
   'negative_prob': 0.023261,
   'sentiment': 2}]}
```
人的情绪是很复杂多样的，一句话也许包含了很多情绪，会根据心态、语气、表情等有不同的感觉，机器很难完全正确识别出人类的情感，因此，情感倾向仅作一个小小的附带记录功能，根据日记形成大致的倾向。
