#### 产品

[20x20下载](https://gitee.com/NFUNM055/ppt/blob/master/20X20ppt.pptx)

| 产品名称  |饮食日记app  |
| -------- |-------- |
| 产品负责人 |刘丽冰 |
| 状态  | 已完成 |

【一句话版本】

简介：“饮食日记”app是一款饮食记录软件，可以帮用户识别果蔬、菜品，同时可以记录、分享自己的的饮食小日记。

【一分钟版本】

“饮食日记”app是一款可以识别果蔬、菜品的饮食记录和分享软件，它运用了图像识别的果蔬识别和菜品识别api，在日常生活中用户遇到不认识的果蔬和菜品都可以通过拍照识别，给用户返回名称、菜品卡路里等信息，解决了用户对果蔬菜品有盲区的痛点。除此，用户还可以通过记录的日记文本，形成自己的心情标签和曲线，和他人相互分享饮食生活，满足用户的分享欲。

#### 市场背景

市场上关于饮食类的app比较多，人们对于“吃”也是比较关注的，记录饮食和记录生活一样重要。但市面上的饮食记录软件目标群体更多为减肥群体和养生群体，记录的更多是食物本身的热量等一些信息，而像写日记一样记录饮食生活的比较少。由于人工智能应用越来越广泛，相继有果蔬、菜品识别的小程序和app出现，但很少有将它运用到其他产品中。所以，决定做一个识别+记录的产品，可以记录用户的饮食生活和情感变化。

#### 加值宣言

“饮食日记”主要是一款可以识别果蔬、菜品的产品，主要面向所有年轻群体。它利用图像识别api中的果蔬识别和菜品识别，帮助用户识别果蔬的名称、菜品的名称、卡路里和其他信息，它既可以记录和分享自己的饮食生活，也可以与其他用户进行交流。另外，饮食和情感也是密不可分的，饮食可以影响情感，情感也会反过来影响饮食，运用自然语言处理api-情感倾向分析，分析饮食日记中编写的文案，得出用户的情感倾向，给日记形成一个情感标签，并在连续记录一个星期后，根据分析出的数值，形成一条情感曲线。


#### 核心价值：

最小可行性产品：通过拍照/上传图片识别果蔬的名称、菜品的名称、卡路里

该app主要分为三个模块【日记】【社区】【我的】，其中【日记】为主要功能。用户可以通过拍照/上传图片的形式，识别果蔬、菜品的图片，不管是生活中吃到的、看到的，还是网上随手存的，都可以在这里识别，如果想要添加到饮食日记中，也可以加上文本内容，形成一个饮食小日记。饮食日记可以识别出果蔬、菜品的名称，以及菜品的相关卡路里等信息，如果希望获得更多的信息则可以通过点击外链到百度百科的信息。

#### 核心价值与用户痛点：

1、生活中，用户可能会遇到自己不熟悉，甚至完全不认识的果蔬、菜品；

2、网上冲浪时，发现一些果蔬/菜品的图片，但不确定是什么；

3、用户想要吃一款美食，但是担心卡路里太高。

#### 人工智能概率性与用户痛点：

图像识别的准确率和稳定性高，且通过深度学习和算法不断提高。实验：通过对日常生活的拍摄的菜品和果蔬图片进行识别后发现，清晰的正面图片一般都能识别成功，较为模糊的图片也能识别成功，非常模糊的图片较难识别成功，但是在返回结果中也有显示成功的名称，对使用的影响不大。【点击可查看更多 [对不同特点图片的识别代码和结果](https://github.com/NFUNM055/api_end_of_term/blob/master/code.md)】

#### 需求列表与人工智能API加值

| 需求                         | 重要程度 | 可用api           |实现可能性|
| ---------------------------- | -------- | ----------------- | ----------------- |
| 知道各种果蔬的名称               | ⭐⭐⭐   | 图像识别-果蔬识别 |高|
| 了解各种菜品的名称、卡路里        | ⭐⭐⭐      | 图像识别-菜品识别 |高|
| 自动记录用户的情感倾向         | ⭐⭐      | 自然语言处理-情感分析 |较高|
| 了解菜品的更多信息，如营养价值、禁忌人群等         | ⭐  | 图像识别-菜品识别 |一般（不是所有识别的菜品都有这些信息）|


#### 产品流程图（若图片无法显示，请点开下方更多原型和交互超链接）

![饮食日记流程图.png](https://upload-images.jianshu.io/upload_images/9460880-db36d40905f310d7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 原型

- 拍照/上传菜品、果蔬的图片
![原型1.PNG](https://upload-images.jianshu.io/upload_images/9460880-8108dea956baee59.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 果蔬、菜品识别（图像识别api-果蔬识别、菜品识别）
![原型2.PNG](https://upload-images.jianshu.io/upload_images/9460880-bd6c707ebba93e12.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 将图片添加到饮食日记；并对输入的文字日记进行情感倾向分析；连续编写7天日记，会在【我的】页形成一条情感曲线。（自然语言处理api-情感倾向分析）
![原型3.PNG](https://upload-images.jianshu.io/upload_images/9460880-312853e0b3db4148.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 分享自己的饮食日记到社区
![原型4.PNG](https://upload-images.jianshu.io/upload_images/9460880-f9eedd77f59bdc30.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##### 口头操作说明

用户注册后即可进入使用，该app需要启动储存权限、拍照权限，用户进入app后的首页是【日记】，在这里用户可以浏览以前的饮食日记或者拍照/上传图片进行识别，并决定是否添加新的饮食日记。第二个模块是【社区】，用户可以将自己的饮食日记分享在这里，也可以在这里查看别人的饮食日记。第三个模块是【我的】，这里是用户的基本信息和情感倾向曲线图，连续添加七天的饮食日记则会形成一条情感曲线。 

- [更多原型和交互点击]( http://nfunm055.gitee.io/api-prototype)

- [原型文档下载](https://github.com/NFUNM055/api-prototype)


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

①

```python
from aip import AipNlp

APP_ID = '18021502'
API_KEY = 'Gp9nWH3HxVt8OAGcyHzXtHTZ'
SECRET_KEY = 'SriOcLgEstfCSy9u5oWR7vrUXpuW8SGQ'

client = AipNlp(APP_ID, API_KEY, SECRET_KEY)
text = "今天天气挺好的，心情也很好，但我说好减肥的，耐不住妈妈煮的鸡煲太好吃了，害我整整吃了两碗饭！"
client.sentimentClassify(text)
```
结果：积极指数：0.98，消极指数：0.02，情感倾向：正向。
```python
{'log_id': 2523262217194262296,
 'text': '今天天气挺好的，心情也很好，但我说好减肥的，耐不住妈妈煮的鸡煲太好吃了，害我整整吃了两碗饭！',
 'items': [{'positive_prob': 0.976739,
   'confidence': 0.948309,
   'negative_prob': 0.023261,
   'sentiment': 2}]}
```
②
```python
from aip import AipNlp

APP_ID = '18021502'
API_KEY = 'Gp9nWH3HxVt8OAGcyHzXtHTZ'
SECRET_KEY = 'SriOcLgEstfCSy9u5oWR7vrUXpuW8SGQ'

client = AipNlp(APP_ID, API_KEY, SECRET_KEY)

text = "今天超级烦，我明明把工作都做完了，刚在饭馆吃着饭，老板突然给电话让我加班。"
client.sentimentClassify(text)
```
结果：积极指数：0.00199102；消极指数：0.998009；情感倾向：负向。
```python
{'log_id': 576788748395683976,
 'text': '今天超级烦，我明明把工作都做完了，刚在饭馆吃着饭，老板突然给电话让我加班。',
 'items': [{'positive_prob': 0.00199102,
   'confidence': 0.995575,
   'negative_prob': 0.998009,
   'sentiment': 0}]}
```
#### api对比：

- 菜品识别api:

1、[百度云菜品识别](https://ai.baidu.com/tech/imagerecognition/dish)：（图片请点击-[百度菜品识别api定价](https://gitee.com/NFUNM055/api_end_of_term/blob/master/%E5%9B%BE%E7%89%87/%E7%99%BE%E5%BA%A6ai%E8%8F%9C%E5%93%81%E8%AF%86%E5%88%AB%E5%AE%9A%E4%BB%B7_mh1578307870992.jpg)；[百度菜品识别api功能](https://gitee.com/NFUNM055/api_end_of_term/blob/master/%E5%9B%BE%E7%89%87/%E7%99%BE%E5%BA%A6%E4%BA%91%E8%8F%9C%E5%93%81%E8%BF%94%E5%9B%9E.jpg)）

百度ai的菜品识别api有免费版和付费版，可以用于个人开发和产品测试，也可以供企业使用。免费的调用量为500次/天，但是并发数不保证；付费版调用数无限制，并发数为10qps，大约0.3元可以调用一千次，调用量越多，收费越便宜。
接口返回有：菜品名称、置信度、卡路里、百科信息等综合信息，而且支持自定义菜品识别。


2、[阿里云菜品识别](https://market.aliyun.com/products/57124001/cmapi032952.html?spm=5176.10695662.1996646101.searchclickresult.5e6d7275Su2P78&aly_as=gTQ_BwDw#sku=yuncode2695200001)：（图片请点击-[阿里云菜品识别api定价](https://gitee.com/NFUNM055/api_end_of_term/blob/master/%E5%9B%BE%E7%89%87/%E9%98%BF%E9%87%8C%E4%BA%91%E8%8F%9C%E5%93%81%E4%BB%B7%E6%A0%BC.jpg)；[阿里云菜品识别api返回](https://gitee.com/NFUNM055/api_end_of_term/blob/master/%E5%9B%BE%E7%89%87/%E9%98%BF%E9%87%8C%E4%BA%91%E8%8F%9C%E5%93%81%E8%BF%94%E5%9B%9E_mh1578309088298.jpg)）

阿里云的菜品识别仅支持50次免费试用，10元才可以调用1000次，价格要比百度贵得多，且成交数和评分都较低，网上能找到的参考文档也较少。返回参数仅有卡路里和名字，返回信息比百度少。

返回结果示例
```
{
  "result": [
    {
      "score": "0.82971",
      "has_calorie": true,
      "calorie": "41",
      "name": "炒青菜"
    },
    {
      "score": "0.085715",
      "has_calorie": true,
      "calorie": "35",
      "name": "白灼菜心"
    },
    {
      "score": "0.084575",
      "has_calorie": true,
      "calorie": "-1",
      "name": "时令蔬菜"
    }
  ]
}
```

3、[京东云菜品识别](https://www.jdcloud.com/cn/products/food-recognition)：（图片请点击-[京东云菜品识别api定价](https://gitee.com/NFUNM055/api_end_of_term/blob/master/%E5%9B%BE%E7%89%87/%E4%BA%AC%E4%B8%9C%E4%BA%91%E8%8F%9C%E5%93%81%E5%AE%9A%E4%BB%B7.jpg)；[京东云菜品识别api功能](https://gitee.com/NFUNM055/api_end_of_term/blob/master/%E5%9B%BE%E7%89%87/%E4%BA%AC%E4%B8%9C%E4%BA%91%E8%8F%9C%E5%93%81%E8%AF%86%E5%88%AB%E5%8A%9F%E8%83%BD_mh1578309120578.jpg);
[京东云公测阶段](https://gitee.com/NFUNM055/api_end_of_term/blob/master/%E5%9B%BE%E7%89%87/%E4%BA%AC%E4%B8%9C%E4%BA%91%E5%85%AC%E6%B5%8B.PNG)）

京东云调用量限制为5000/日，现在处于公测阶段，可以免费试用，但由于开发时间不长，目前的不稳定性和不成熟性较高。而百度菜品识别api已经过了这一阶段，和较多公司有了合作案例。京东云仅支持检测中餐菜品，且识别的返回结果只有菜品名称。


4、[聚合数据](https://www.juhe.cn/docs/api/id/372)

接口地址：http://apis.juhe.cn/dishDetect/index

返回结果和百度的相似。另外，聚合数据还有[菜谱大全api](https://www.juhe.cn/docs/api/id/46)，对饮食类产品较友好。但是购买至少需要1000元，不适合个人开发者，比较适合企业使用。

- 果蔬识别api:

1、[百度果蔬识别](https://ai.baidu.com/tech/imagerecognition/ingredient)

可以用于个人开发和产品测试，也可以供企业使用。免费的调用量一次性共有3000次。开通付费后无限制。返回的结果仅有果蔬名字。

2、[聚合数据](https://www.juhe.cn/docs/api/id/393)

至少需要1000购买，不适合个人开发者，比较适合企业使用，约0.02元调用一次。

3、腾讯云、阿里云的图像识别功能可以为所有种类的图片进行识别，包括果蔬、菜品，但没有细分种类，且返回信息少。

#### 使用后风险报告：

所使用的api为百度图像识别-菜品识别api和果蔬识别api、自然语言处理api。

市场竞争程度：[百度图像识别api](https://ai.baidu.com/ai-doc/IMAGERECOGNITION/Kk3bcxbxj)是目前找到划分最为细的一个，并且官方的支持语言多。更多竞争者——阿里云、腾讯云、京东云、华为云。

返回结果：菜品识别和果蔬识别的返回结果并没有十分丰富，而且不是所有识别的图片都会有禁忌人群、营养成分这些信息，水果蔬菜的识别结果也仅有名称。

定价：如上所示，定价比大多数api便宜，且免费次数多。对个人和初创公司友好，资金缺乏时，可以使用免费版测试产品。

准确性和限制：图像识别的准确性比较高，但对图像识别有限制：[图像识别限制](https://gitee.com/NFUNM055/api_end_of_term/blob/master/%E5%9B%BE%E7%89%87/%E5%9B%BE%E5%83%8F%E8%AF%86%E5%88%AB%E9%99%90%E5%88%B6.PNG)

目前来说，百度api发展得比较好，用户多，但仍然存在一些可以完善得地方。




