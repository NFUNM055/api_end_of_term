#### 产品

| 产品名称  |饮食日记app  |
| -------- |-------- |
| 产品负责人 |刘丽冰 |
| 状态  | 未完成 |


简介：一个饮食记录软件，帮你识别果蔬、菜品，记录你的饮食及心情。


#### 痛点：

1、不知道某些果蔬、菜品的名称

2、找不到专门的app记录自己的饮食生活

3、

#### 加值宣言

民以食为天，饮食是生活中的一部分，记录饮食和记录生活一样重要。

图像识别-果蔬识别和菜品识别api：拍摄/上传本地图片，放置饮食日记中，可以帮助用户辨别各种果蔬、菜品的名称等信息，并且形成标签；
自然语言处理-情感倾向分析：饮食和情感是密不可分的，饮食可以影响情感，情感也会反过来影响饮食。根据用户在饮食日记编写的文字，分析用户的情感倾向，给日记形成一个情感标签。

#### 核心价值：

最小可行性产品：识别果蔬、菜品的名称

该app主要分为三个模块【推荐】【饮食日记】【我的】，其中【饮食日记】为主要功能。用户可以通过拍照/上传图片的形式，识别果蔬、菜品的图片，不管是生活中吃到的、看到的，还是网上随手存的，都可以放入饮食日记中，饮食日记可以识别出果蔬、菜品的名称，以及菜品的相关卡路里等信息，如果希望获得更多的信息则可以通过点击外链到百科百科的信息。

#### 需求列表

| 需求                         | 重要程度 | 可用api           |实现可能性|
| ---------------------------- | -------- | ----------------- | ----------------- |
| 识别各种果蔬的名称               | ⭐⭐⭐   | 图像识别-果蔬识别 |高|
| 识别各种菜品的名称         | ⭐⭐⭐      | 图像识别-菜品识别 |高|
| 分析日记文字的情感倾向         | ⭐⭐      | 自然语言处理-情感分析 |较高|
| 一键推荐饮食|⭐ |从用户饮食日记的记录中提取推荐|不会|
| 了解菜品的更多信息，如禁忌人群，卡路里等         | ⭐  | 图像识别-菜品识别 |一般（不是所有识别的菜品都有这些信息）|


#### 原型

![主要功能原型](https://images.gitee.com/uploads/images/2020/0101/042311_684f1a99_1648156.png "主要功能流程图.png")


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
3、菜品识别——鸡肉煲
```python
import requests
import base64

request_url = "https://aip.baidubce.com/rest/2.0/image-classify/v2/dish"
f = open('jibao.jpg', 'rb')
img = base64.b64encode(f.read())

params = {"image":img,"top_num":1,"filter_threshold":0.95,"baike_num":0}
access_token = '24.2a1c09a400df3dcf3bfe1491bc6ab4e8.2592000.1578035412.282335-17927505'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/x-www-form-urlencoded'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())
```
结果——识别成功
```python
{'log_id': 1119793080360029112, 'result_num': 6, 'result': [{'calorie': '111', 'has_calorie': True, 'name': '鸡肉煲', 'probability': '0.419609'}, {'calorie': '162', 'has_calorie': True, 'name': '黄焖鸡', 'probability': '0.269348'}, {'has_calorie': False, 'name': '麻辣瓦香鸡', 'probability': '0.0402247'}, {'calorie': '260', 'has_calorie': True, 'name': '猪蹄', 'probability': '0.0341583'}, {'calorie': '223', 'has_calorie': True, 'name': '排骨煲', 'probability': '0.0267608'}, {'calorie': '128', 'has_calorie': True, 'name': '大盘鸡', 'probability': '0.0221576'}]}
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
