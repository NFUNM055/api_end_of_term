#### 以下识别的图片均为日常生活中拍摄的。
### 1、菜品识别
```
import requests
import base64

request_url = "https://aip.baidubce.com/rest/2.0/image-classify/v2/dish"
f = open('nw.jpg', 'rb')
img = base64.b64encode(f.read())

params = {"image":img,"top_num":1,"filter_threshold":0.95,"baike_num":7}
access_token = '24.e264db18593145433bf09c4f41a16e54.2592000.1580824242.282335-17927505'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/x-www-form-urlencoded'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())
```
### 图片特点：正面、清晰；识别结果：成功。
```
{'log_id': 5923204416417949319, 'result_num': 6, 'result': [{'calorie': '233', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E9%A6%99%E9%94%85%E7%89%9B%E8%9B%99/12996899', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/79f0f736afc37931b4558571eec4b74543a911ac.jpg', 'description': '香锅牛蛙是一款家常菜品，制作原料主要有牛蛙、海带、莴笋、木耳、香菇、藕、土豆、五花肉、豆腐皮等。'}, 'probability': '0.544046', 'name': '香锅牛蛙'}, {'calorie': '173', 'has_calorie': True, 'baike_info': {}, 'probability': '0.0969501', 'name': '石锅蛙'}, {'calorie': '81', 'has_calorie': True, 'baike_info': {}, 'probability': '0.0842204', 'name': '美蛙'}, {'calorie': '325', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E6%B3%A1%E6%A4%92%E7%89%9B%E8%9B%99/3804722', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/d4628535e5dde71119d376baa7efce1b9d16617c.jpg', 'description': '泡椒牛蛙是一道色香味俱全的川渝地区的名菜，属于川菜系。最常见又易烹制，成菜后味咸鲜，肉细嫩，色红亮，泡菜香气浓郁。牛蛙宰杀去头去皮去内脏洗净，斩成块，用盐、胡椒粉、干豆粉、料酒上浆码味。泡红辣椒去蒂去籽切成节，大葱洗净切成节，泡姜切成姜米。炒锅下油烧至七成热，将牛蛙下锅滑溜断生捞起。炒锅内下少许油烧热，下泡姜米、泡椒节炒出香味，下牛蛙，烹入料酒，放味精、大葱节簸转起锅装盘即可。'}, 'probability': '0.079948', 'name': '泡椒牛蛙'}, {'calorie': '166', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E7%9F%B3%E9%94%85%E9%B8%A1/12786181', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/a8ec8a13632762d0228cd8e6aeec08fa513dc63d.jpg', 'description': '石锅鸡是西藏菜品。 以手掌参、土鸡等原料，经这种石锅慢火炖制的石锅鸡风味非常独特，汤味有一股淡淡的药材清香，鸡肉嫩而有弹性。炖鸡用的石锅是用一种叫做“皂石”的云母石制成，加工时要求下手力道匀称，一旦心急，皂石容易被凿穿，这种石锅售价也比较昂贵。墨绿色的云母石锅，保温性特别好。'}, 'probability': '0.0662824', 'name': '石锅鸡'}, {'calorie': '81', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E7%89%9B%E8%9B%99/62782', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/86d6277f9e2f0708fc7d20c7ec24b899a801f2f9.jpg', 'description': '牛蛙(Rana catesbiana Shaw)属于两栖纲(Amphibia)、无尾目(Anura)、蛙科(Ranidae)，是一种大型食用蛙，其肉质细嫩，味道鲜美，营养丰富，具有一定的药用价值。牛蛙，俗名美国水蛙，个体硕大，生长快，产量高，原产于北美洲和墨西哥等地，目前己遍及世界各大洲，是各地食用蛙中的主要养殖种类。牛蛙 原产于北美，因其鸣叫声宏亮酷似牛叫而得名。1959年牛蛙从古巴引入我国，九十年代左右开始在我国被大范围推广养殖。近年来，牛蛙已成为我国水产养殖重要的名特水产品之一。'}, 'probability': '0.0330142', 'name': '牛蛙'}]}
```

```
import requests
import base64

request_url = "https://aip.baidubce.com/rest/2.0/image-classify/v2/dish"
f = open('非正面.jpg', 'rb')
img = base64.b64encode(f.read())

params = {"image":img,"top_num":1,"filter_threshold":0.95,"baike_num":7}
access_token = '24.e264db18593145433bf09c4f41a16e54.2592000.1580824242.282335-17927505'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/x-www-form-urlencoded'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())
```
### 图片特定：非正面、清晰；结果：识别成功。
```
{'log_id': 8976206461048185095, 'result_num': 6, 'result': [{'has_calorie': False, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E7%81%AB%E9%94%85/274015', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/91529822720e0cf3c9e46ed90746f21fbe09aa84.jpg', 'description': '火锅(英语：Hot Pot)，古称“古董羹”，因食物投入沸水时发出的“咕咚”声而得名，它是中国独创的美食，历史悠久，是一种老少皆宜的食物。周代的鼎器应是火锅最早的雏形，据考证，战国时期即有火锅，时人以陶罐为锅，到宋代，火锅的吃法在民间已十分常见，南宋林洪的《山家清供》食谱中，便有同友人吃火锅的介绍。元代，火锅流传到蒙古一带，用来煮牛羊肉。到清代，火锅不仅在民间流行，而且成了一道著名的“宫廷菜”，用料是山鸡等野味。火锅一般是指以锅为器具，以热源烧锅，以水或汤烧开来涮煮各类食物的烹调方式，同时亦可指这种烹调方式所用的锅具。其特色为边煮边吃，或是锅本身具有保温效果，吃的时候食物仍热气腾腾，汤物合一。世界各地均有类似的料理，但主要在东亚地方特别盛行。火锅现吃现烫，辣咸鲜，油而不腻，解郁除湿，适于山川之气候，今发展为鸳鸯锅，麻辣、清淡各别，各取所需，根据个人的喜欢加不同的汤料、食物，老少咸宜，至冬之佳品。典型的火锅食材包括各种肉类、海鲜类、蔬菜类、豆制品类、菌菇类、蛋类制品、粉丝等，将其放入煮开的清水或特制的高汤锅底烫熟后食用。有些吃法还会蘸上调味料 一起食用。'}, 'probability': '0.953974', 'name': '火锅'}, {'has_calorie': False, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E9%B8%B3%E9%B8%AF%E7%81%AB%E9%94%85/338902', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/bd3eb13533fa828b979dd524ff1f4134960a5abe.jpg', 'description': '鸳鸯火锅，是一道美味可口的名吃，属于渝派川菜系。成菜风味别致，麻辣鲜香，鲜醇浓厚，各有特色。鸳鸯火锅，是以传统毛肚火锅的红汤卤和宴席菊花火锅的清汤卤，两者合并改制而成的重庆创新火锅。此品原名“双味火锅”。为1983年重庆队参加全国第一届烹饪大赛的参赛菜品，由阎文俊取名设计、特级厨师陈志刚制作。这种火锅用铜片隔成两半，造成一个太极图形，一边放清汤卤，一边放红汤卤，入锅烫涮的原料可随人意。1985年，熊四智将“双味火锅”改名为“鸳鸯火锅”，更富有文化韵味和饮食情趣。爱新觉罗·溥杰作为1983年全国烹饪大赛的评委顾问，曾对此品评价说：“这个菜很好，好就好在有发展。它巧妙地将重庆传统的红汤火锅,清汤火锅汇于一锅，风味别致，颇有特色。更可取的是这个菜的容器，这种太极图锅耐人寻味。”'}, 'probability': '0.0409393', 'name': '鸳鸯火锅'}, {'calorie': '130', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E6%B5%B7%E9%B2%9C%E7%81%AB%E9%94%85/3040729', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/e824b899a9014c08125289a9047b02087bf4f455.jpg', 'description': '海鲜火锅是中国传统的民间美食，然而随着消费者对餐饮的要求提高，传统的海鲜火锅已不能满足大众消费。全新的海鲜火锅“裸烹”成为火锅餐饮行业的新法宝，纯天然火锅新模式，在国内火锅餐饮门店掀起了一波海鲜火锅热潮，深受人们欢迎。所谓海鲜火锅“裸烹”，即是选用上等的海鲜食材入料，品味原汁原味的海鲜火锅，纯天然不添加任何添加剂，如海鲜滑类、以及海鲜原料等，在秋季到来时，品一锅清淡鲜美的海鲜火锅，绝对的极品美味。国内的海鲜产品领导品牌亚洲渔港实为海鲜火锅"裸烹"的推手之一,提供了大量的火锅原料，裙带菜嫩叶，牛角鱿鱼花，月牙贝，大海虾，蟹足棒，大海螺，全籽乌贼，特色墨鱼滑，美味鲜虾滑，鲜美纯虾滑，大连花蚬滑，扇贝滑，鲍鱼滑等优质的食材。海鲜火锅即是以海鲜为主要食材，用火锅的方式烹饪。这种做法可以避免多余的调味料和添加剂，保持海鲜原有的风味。'}, 'probability': '0.00152203', 'name': '海鲜火锅'}, {'calorie': '367', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E4%B8%B2%E4%B8%B2%E9%A6%99/26410', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/8435e5dde71190ef7c54d58cc01b9d16fdfa6031.jpg', 'description': '串串香，起源于四川成都，不仅是四川地区的特色传统小吃之一，也是草根美食最大众化的体现，串串香实际上是火锅的另一种形式，所以人们又往往称其为小火锅。“串串香”名字的由来是因为这是一种以竹签串上各种菜，将其放进滚烫的火锅中涮着吃的小吃。串串香以其独特的魅力和鲜明的特色遍布于全国众多城市，“麻辣烫”亦是其变体，可以说只要有人的地方就有串串香的存在，甚至在一定程度上，串串香已成为四川味道的代表之一。'}, 'probability': '0.000759631', 'name': '串串香'}, {'has_calorie': False, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E6%97%A5%E5%BC%8F%E7%81%AB%E9%94%85/7605087', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/9f2f070828381f30a61c7fb6ad014c086e06f0ac.jpg', 'description': '日式火锅是日本的传统饮食方式，古而有之，历史久远，味美新鲜。分为寿喜烧火锅、海鲜火锅、山产火锅等分类，讲求使用纯美的高汤调味、使用药味佐料。拥有美味营养的特点。'}, 'probability': '0.000604114', 'name': '日式火锅'}, {'has_calorie': False, 'baike_info': {}, 'probability': '0.000389818', 'name': '菌汤锅'}]}
```

```
import requests
import base64

request_url = "https://aip.baidubce.com/rest/2.0/image-classify/v2/dish"
f = open('zm.jpg', 'rb')
img = base64.b64encode(f.read())

params = {"image":img,"top_num":1,"filter_threshold":0.95,"baike_num":7}
access_token = '24.e264db18593145433bf09c4f41a16e54.2592000.1580824242.282335-17927505'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/x-www-form-urlencoded'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())
```
### 图片特定：正面、模糊；结果：图片为土豆鸡煲，结果有不够准确，但并不离谱。
```
{'log_id': 3064502548632558567, 'result_num': 6, 'result': [{'calorie': '162', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E9%BB%84%E7%84%96%E9%B8%A1/1190323', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/738b4710b912c8fcc3287c65f6039245d78821ba.jpg', 'description': '黄焖鸡米饭又叫香鸡煲、浓汁鸡煲饭，属于鲁菜系家常菜品，起源于山东省济南市。主要食材是鸡腿肉，配以青椒、土豆、香菇等焖制而成，味道美妙，具有肉质鲜美嫩滑的特点。'}, 'probability': '0.227091', 'name': '黄焖鸡'}, {'calorie': '126', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E9%B8%A1%E8%82%89%E7%82%96%E8%98%91%E8%8F%87/4241076', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/0b7b02087bf40ad16944f9b3592c11dfa9ecce39.jpg', 'description': '鸡肉炖蘑菇，营养搭配，荤素均衡，鸡肉香嫩，蘑菇入味香甜'}, 'probability': '0.193827', 'name': '鸡肉炖蘑菇'}, {'calorie': '128', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E6%9D%BF%E6%A0%97%E7%83%A7%E9%B8%A1/2142755', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/e824b899a9014c088b1f32eb007b02087bf4f45c.jpg', 'description': '板栗烧鸡，是一道传统名菜，属东北菜、川菜、湘菜等。菜品具有鸡肉鲜滑、板栗香甜、汁浓醇厚、色泽红亮、美观大方的特点。'}, 'probability': '0.153276', 'name': '板栗烧鸡'}, {'calorie': '216', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E6%A0%97%E5%AD%90%E9%B8%A1/2897613', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/472309f79052982288884eaed5ca7bcb0a46d420.jpg', 'description': '栗子鸡是山东济南传统的名菜，属于鲁菜系。此菜栗子绵软，鸡肉嫩烂，色泽红亮，味道香浓。'}, 'probability': '0.051465', 'name': '栗子鸡'}, {'calorie': '87', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E8%9B%8B%E5%8C%85%E9%A5%AD/21763', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/9d82d158ccbf6c81f7fe3d9db33eb13532fa40fd.jpg', 'description': '蛋包饭是日本一种比较普通且很受青睐的主食，由蛋皮包裹炒饭而成的菜肴。一般是将鸡蛋煎成厚薄均匀的蛋皮，再放上炒好的炒饭、韩式辣椒酱、番茄酱、色拉油和其他各种材料包好制成。 蛋包饭不论是在韩国，日本或台湾，都是相当受到欢迎的料理，不只是一道家庭料理，也有餐厅供应，甚至还有专卖店专卖。在中国大陆地区也有部分餐厅出售。'}, 'probability': '0.0324904', 'name': '蛋包饭'}, {'calorie': '87', 'has_calorie': True, 'baike_info': {'baike_url': 'http://baike.baidu.com/item/%E5%92%96%E5%96%B1%E9%A5%AD/3183394', 'image_url': 'http://imgsrc.baidu.com/baike/pic/item/8c1001e93901213fa904258f5ae736d12f2e95a9.jpg', 'description': '咖喱饭是一种美食，主要材料有牛肉、猪肉、鸡肉等，辅料有土豆、胡萝卜、洋葱、咖喱块等，口味属于咖喱味。咖喱饭常常被用来做主食。"咖喱”一词来源于坦米尔语，是“许多的香料加在一起煮”的意思，据说咖喱的故乡在印度。'}, 'probability': '0.0257178', 'name': '咖喱饭'}]}
```

## 2、水果识别
```
import requests
import base64

request_url = "https://aip.baidubce.com/rest/2.0/image-classify/v1/classify/ingredient"
f = open("ft.jpg", 'rb')
img = base64.b64encode(f.read())

params = {"image":img}
access_token = '24.e264db18593145433bf09c4f41a16e54.2592000.1580824242.282335-17927505'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/x-www-form-urlencoded'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())
```
### 图片特点：清晰，但水果表面刮痕多；结果：识别错误，该水果为番石榴。
```
{'log_id': 1517907761014619271, 'result_num': 5, 'result': [{'score': 0.3184604346752167, 'name': '芒果'}, {'score': 0.10972527414560318, 'name': '青木瓜'}, {'score': 0.1080741211771965, 'name': '青柚'}, {'score': 0.08137264847755432, 'name': '佛手瓜'}, {'score': 0.07111751288175583, 'name': '芭乐'}]}
```

```
import requests
import base64

request_url = "https://aip.baidubce.com/rest/2.0/image-classify/v1/classify/ingredient"
f = open("jz.jpg", 'rb')
img = base64.b64encode(f.read())

params = {"image":img}
access_token = '24.e264db18593145433bf09c4f41a16e54.2592000.1580824242.282335-17927505'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/x-www-form-urlencoded'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())
```
### 图片特点：清晰；结果：识别正确。
```
{'log_id': 7806291462593504551, 'result_num': 5, 'result': [{'score': 0.4245695173740387, 'name': '沙糖桔'}, {'score': 0.3499835431575775, 'name': '柑橘'}, {'score': 0.09559653699398041, 'name': '砂糖橘'}, {'score': 0.03903702646493912, 'name': '金桔'}, {'score': 0.015715058892965317, 'name': '马水桔'}]}
```

```
import requests
import base64

request_url = "https://aip.baidubce.com/rest/2.0/image-classify/v1/classify/ingredient"
f = open("mg.jpg", 'rb')
img = base64.b64encode(f.read())

params = {"image":img}
access_token = '24.e264db18593145433bf09c4f41a16e54.2592000.1580824242.282335-17927505'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/x-www-form-urlencoded'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())
```
### 图片特点：清晰，水果为切开状态；结果：识别正确。
```
{'log_id': 1067297514450624551, 'result_num': 5, 'result': [{'score': 0.4599226713180542, 'name': '木瓜'}, {'score': 0.28723862767219543, 'name': '青木瓜'}, {'score': 0.1643613874912262, 'name': '柿子'}, {'score': 0.040361396968364716, 'name': '灯笼辣椒'}, {'score': 0.029575983062386513, 'name': '陇南甜柿'}]}
```

## 3、蔬菜识别
```
import requests
import base64

request_url = "https://aip.baidubce.com/rest/2.0/image-classify/v1/classify/ingredient"
f = open("kg.jpg", 'rb')
img = base64.b64encode(f.read())

params = {"image":img}
access_token = '24.e264db18593145433bf09c4f41a16e54.2592000.1580824242.282335-17927505'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/x-www-form-urlencoded'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())
```
### 图片特点：模糊；结果：识别正确。
```
{'log_id': 8325935145454595207, 'result_num': 5, 'result': [{'score': 0.9989374279975891, 'name': '苦瓜'}, {'score': 0.0010265207383781672, 'name': '非果蔬食材'}, {'score': 2.190102713939268e-05, 'name': '菜瓜'}, {'score': 3.201428398824646e-06, 'name': '丝瓜'}, {'score': 2.0323604985605925e-06, 'name': '佛手瓜'}]}
```

```
import requests
import base64

request_url = "https://aip.baidubce.com/rest/2.0/image-classify/v1/classify/ingredient"
f = open("lb.jpg", 'rb')
img = base64.b64encode(f.read())

params = {"image":img}
access_token = '24.e264db18593145433bf09c4f41a16e54.2592000.1580824242.282335-17927505'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/x-www-form-urlencoded'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())
```
### 图片特点：清晰；结果：识别正确。
```
{'log_id': 1289192220389714151, 'result_num': 5, 'result': [{'score': 0.8441018462181091, 'name': '萝卜'}, {'score': 0.07124374806880951, 'name': '胡萝卜'}, {'score': 0.025900157168507576, 'name': '山药'}, {'score': 0.014991219155490398, 'name': '辣根'}, {'score': 0.008018109016120434, 'name': '红薯'}]}
```

```
import requests
import base64

request_url = "https://aip.baidubce.com/rest/2.0/image-classify/v1/classify/ingredient"
f = open("cc.jpg", 'rb')
img = base64.b64encode(f.read())

params = {"image":img}
access_token = '24.e264db18593145433bf09c4f41a16e54.2592000.1580824242.282335-17927505'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/x-www-form-urlencoded'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())
```
### 图片特点：非常模糊；结果：前四个结果识别错误，但最后一个结果出现了正确名称“生菜”
```
{'log_id': 1552094962786334727, 'result_num': 5, 'result': [{'score': 0.6891205310821533, 'name': '非果蔬食材'}, {'score': 0.12399787455797195, 'name': '羽衣甘蓝'}, {'score': 0.06171886995434761, 'name': '苦苣'}, {'score': 0.02874620631337166, 'name': '苦菊'}, {'score': 0.021071545779705048, 'name': '生菜'}]}
```
