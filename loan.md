#  API 文档
##### version __1.0.0__
##### 内网接口地址 http://daichao.huoshanqianbao.com

<br>
### I ChangeLog

  - 2019-5-19
    - 初始化

### II 目录
- [x] 1.[新增接口](#1新增接口)
  - [x] [1.1 会员特权列表](#11-会员特权列表)
  - [x] [1.2 会员购买套餐](#12-会员购买套餐)
  - [x] [1.3 资金流水记录](#13-资金流水记录)
  - [x] [1.4 获取用户的银行卡](#14-获取用户的银行卡)
  - [x] [1.5 修改用户的银行卡信息](#15-修改用户的银行卡信息)
  - [x] [1.6 提现](#16-提现)
  - [x] [1.7 获取用户的申请进度](#17-获取用户的申请进度)
- [x] 2.[修改的接口](#2修改的接口)
  - [x] [2.1 登录注册校验](#21-登录注册校验)
  - [x] [2.2 个人信息查询](#22-个人信息查询)
  - [x] [2.3 我的申请查询接口](#23-我的申请查询接口)
  - [x] [2.4 热门推荐](#24-热门推荐)
  - [x] [2.5 产品搜索](#25-产品搜索)
  - [x] [2.6 产品过滤](#26-产品过滤)
- [x] 3.[用户画像的接口](#3用户画像的接口)
  - [x] [2.1 登录注册校验](#21-登录注册校验)
  - [x] [2.2 查询是否完成资料](#22-查询是否完成资料)
  - [x] [2.3 提交资料](#23-提交资料)
  - [x] [3.4 判断用户是不是会员](#24-判断用户是不是会员)
  - [x] [3.5 会员基础列表(开通前页面)](#24- 会员基础列表(开通前页面))
  - [x] [3.6 购买页面](#24-购买页面)
  - [x] [3.7 支付接口](#24-判断用户是不是会员)
  - [x] [3.8 查看是否实名认证](#24-判断用户是不是会员)
  - [x] [3.9 实名认证接口](#24-判断用户是不是会员)
  - [x] [4.0 会员信息(开通后页面)](#24-判断用户是不是会员)
  - [x] [4.1 查询历史报告](#41-查询历史报告)
  - [x] [4.2 查询实名认证信息](#42-查询实名认证信息)
- [x] 4.[桔子API接口](#4桔子API接口)
  - [x] [4.1 身份证正反面上传](#41-身份证正反面上传)
  - [x] [4.2 保存身份认证信息](#42-保存身份认证信息)
  - [x] [4.3 产品详情](#43-产品详情)
  - [x] [4.4 查询身份认证信息](#44-查询身份认证信息)
  - [x] [4.5 渠道用户注册](#45-渠道用户注册)
  - [x] [4.6 用户准入接口](#46-用户准入接口)
  - [x] [4.7 查询默认绑卡接口](#47-查询默认绑卡接口)
  - [x] [4.8 查询订单列表](#48-查询订单列表)
  - [x] [4.9 接收绑卡验证码接口](#49-接收绑卡验证码接口)
  - [x] [5.0 用户银行卡绑卡接口](#50-用户银行卡绑卡接口)
  - [x] [5.1 查询用户额度](#51-查询用户额度)
  - [x] [5.2 分期试算](#52-分期试算)
------

### 1.新增接口

#### 1.1 会员特权列表
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/app/memberPay/memberPrivilegeList</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>获取会员特权列表数据</td>
    </tr>
  </tbody>
</table>

##### 入参
无

##### data出参

参数名|非空|类型|说明
---|---|---|---
imgUrl | 是 | String| 图标地址
content | 是 | String| 内容


sample:
```json
  "data": [
      {
        "content": "会员包下款",
        "imgUrl": "http://hyj-pro.oss-cn-shenzhen.aliyuncs.com//banner/img/1546597345872.jpg"
      },
      {
        "content": "会员包下款",
        "imgUrl": "http://hyj-pro.oss-cn-shenzhen.aliyuncs.com//banner/img/1546597345872.jpg"
      }
    ]
```
------


#### 1.2 会员购买套餐
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/app/memberPay/userSetMealList</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>会员购买套餐</td>
    </tr>
  </tbody>
</table>

##### 入参
无

##### data出参

参数名|非空|类型|说明
---|---|---|---
id | 是 | String| 会员套餐ID
content | 是 | String| 说明
adver | 是 | String| 广告语
originalPrice | 是 | String| 原价
concessionalRate | 是 | String| 优惠价


sample:
```json
  "data": [
      {
		"id": 1,
		"content": "6个月会员",
		"adver": "33元/月",
        "originalPrice": "228",
        "concessionalRate": "198"
      },
      {
        "id": 1,
		"content": "6个月会员",
		"adver": "33元/月",
        "originalPrice": "228",
        "concessionalRate": "198"
      }
    ]
```
------

#### 1.3 资金流水记录
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/app/memberPay/moneyRecord</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>资金流水记录</td>
    </tr>
  </tbody>
</table>

##### bizParams入参
参数名|非空|类型|说明
---|---|---|---
userId | 是 | String| 用户编号

##### data出参

参数名|非空|类型|说明
---|---|---|---
type | 是 | String| 1 进账 2出账
content | 是 | String| 说明
state | 是 | String| 0 待入账 1 以入账
money | 是 | String| 金额
updateTime | 是 | String| 时间


sample:
```json
  "data": [
      {
		"type": 1,
		"content": "在宜入贷成功下款2000元,获得20元佣金",
		"state": 1,
        "money": "20",
        "updateTime": "2019-5-19 01:08"
      },
      {
        "type": 1,
		"content": "在宜入贷成功下款2000元,获得20元佣金",
		"state": 1,
        "money": "20",
        "updateTime": "2019-5-19 01:08"
      }
    ]
```
------

#### 1.4 获取用户的银行卡
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/app/memberPay/getUserBankInfo</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>获取用户的银行卡</td>
    </tr>
  </tbody>
</table>

##### bizParams入参
参数名|非空|类型|说明
---|---|---|---
userId | 是 | String| 用户编号

##### data出参

参数名|非空|类型|说明
---|---|---|---
name | 是 | String| 姓名 该接口需要做非空判断 如果没有获取到值就在银行卡模块处提示用户点击完善银行卡信息
bank | 是 | String| 银行
openBank | 是 | String|开户行
idCard | 是 | String| 卡号
phone | 是 | String| 银行预留手机号


sample:
```json
  "data": {
		"name": "何举",
		"bank": "中国民生银行",
		"openBank": "重庆南岸区南坪支行",
        "idCard": "6234567854234567",
        "phone": "18523171796"
   }
```
------

#### 1.5 修改用户的银行卡信息
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/app/memberPay/updateUserBankInfo</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>修改用户的银行卡信息</td>
    </tr>
  </tbody>
</table>

##### bizParams入参
参数名|非空|类型|说明
---|---|---|---
userId | 是 | String| 用户编号
name | 是 | String| 姓名
bank | 是 | String| 银行
openBank | 是 | String|开户行
idCard | 是 | String| 卡号
phone | 是 | String| 银行预留手机号

##### data出参
无


sample:
```json

```
------

#### 1.6 提现
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/app/memberPay/cashWithdrawal</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>提现</td>
    </tr>
  </tbody>
</table>

##### data入参
参数名|非空|类型|说明
---|---|---|---
userId | 是 | String | 用户编号
cashWithdrawalMoney | 是 | String | 用户编号
name | 是 | String| 姓名
bank | 是 | String| 银行
openBank | 是 | String|开户行
idCard | 是 | String| 卡号
phone | 是 | String| 银行预留手机号


##### 出参
无


sample:
```json

```
------

#### 1.7 获取用户的申请进度
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/app/memberPay/moneyRecord</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>获取用户的申请进度</td>
    </tr>
  </tbody>
</table>

##### bizParams入参
参数名|非空|类型|说明
---|---|---|---
orderNo | 是 | String| 申请记录编号

##### data出参

参数名|非空|类型|说明
---|---|---|---
content | 是 | String| 说明
time | 是 | String| 时间


sample:
```json
  "data": [
      {
		"content": "等待审核",
        "time": "2019-5-19 01:08"
      },
      {
		"content": "审核中",
        "time": "2019-5-19 01:08"
      }
    ]
```
------

### 2.修改的接口

#### 2.1 登录注册校验
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/app/member/login</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>登录注册校验</td>
    </tr>
  </tbody>
</table>

##### 入参
没变化


##### data出参新增参数

参数名|非空|类型|说明
---|---|---|---
hyFalg | 是 | String | 0 非会员 1 会员
hyStartTime | 是 | String | 会员开始时间
hyEndTime | 是 | String | 会员结束时间
money | 是 | String | 余额

sample:
```json

```

------

#### 2.2 个人信息查询
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/app/member/querydetail</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>个人信息查询</td>
    </tr>
  </tbody>
</table>

##### 入参
没变化


##### data出参新增参数

参数名|非空|类型|说明
---|---|---|---
hyFalg | 是 | String | 0 非会员 1 会员
hyStartTime | 是 | String | 会员开始时间
hyEndTime | 是 | String | 会员结束时间
money | 是 | String | 余额

sample:
```json

```

------

#### 2.3 我的申请查询接口
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/app/product/applylist</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>我的申请查询接口</td>
    </tr>
  </tbody>
</table>

##### 入参
没变化


##### data出参新增参数

参数名|非空|类型|说明
---|---|---|---
firstPartyState | 是 | int | 该记录状态 0 待审核 1 审核中 2 审核通过 3 审核失败 4 等待放款 5 以放款
firstPartyContent | 是 | String | 状态说明

sample:
```json

```

------

#### 2.4 热门推荐
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/app/product/hotquery</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>热门推荐</td>
    </tr>
  </tbody>
</table>

##### 入参
没变化


##### data出参新增参数

参数名|非空|类型|说明
---|---|---|---
labelString | 是 | String | 标签(做非空判断,是一个字符串,用蓝色的圆角长方形框框包起来放在产品名后面,为空就不显示)

sample:
```json

```

------

#### 2.5 产品搜索
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/app/product/search</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>产品搜索</td>
    </tr>
  </tbody>
</table>

##### 入参
没变化


##### data出参新增参数

参数名|非空|类型|说明
---|---|---|---
labelString | 是 | String | 标签(做非空判断,是一个字符串,用蓝色的圆角长方形框框包起来放在产品名后面,为空就不显示)

sample:
```json

```

------

#### 2.6 产品过滤
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/app/product/filterquery</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>产品过滤</td>
    </tr>
  </tbody>
</table>

##### 入参
没变化


##### data出参新增参数

参数名|非空|类型|说明
---|---|---|---
labelString | 是 | String | 标签(做非空判断,是一个字符串,用蓝色的圆角长方形框框包起来放在产品名后面,为空就不显示)

sample:
```json

```

------
### 3.用户画像的接口

#### 3.1 字段列表
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/UserPortrait/queryFieldAll.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>字段列表</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
token | 是 | String| 用户token

##### data出参

参数名|非空|类型|说明
---|---|---|---
modularId | 是 | Integer| 模块ID
modularName | 是 | String| 模块名称
submoduleId | 是 | Integer| 子模块名称
submoduleName | 是 | String| 子模块名称
fieldId | 是 | Integer| 字段ID
chName | 是 | String| 中文字段名称
enName | 是 | String| 英文字段名称
fieldType | 是 | Integer| 字段类型
value | 是 | String| 字段值 fieldType=3时为字段选项id
fieldValId | 是 | Integer| 字段选项ID
fieldVal | 是 | Integer| 字段选项值

sample:
```json
  "list": [
    {
	"modularId": 21,
	"modularName": "基本信息",
	"submoduleList": [{
				"submoduleId": 9,
				"submoduleName": "个人信息",
				"fieldList": [{
							"fieldId": 5,
							"chName": "婚姻状态",
							"enName": "hyzt",
							"fieldType": 3,
							"value": "",
							"fieldVal": [{
									"fieldValId": 26,
									"fieldVal": "已婚"
								},
								{
									"fieldValId": 27,
									"fieldVal": "未婚"
								}
							]
						}
    ]
```
------
#### 3.2 查询是否完成资料
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/UserPortrait/isFillInData.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>查询是否完成资料</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
token | 是 | String| 用户token

##### data出参

参数名|非空|类型|说明
---|---|---|---
flag | 是 | Integer| 是否完成资料 //1:已认证  2:未认证

sample:
```json
  "data":{
    "flag":1
  }
```
------
#### 3.3 提交资料
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/UserPortrait/saveInfo.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>提交资料</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
token | 是 | String| 用户token

##### data出参

参数名|非空|类型|说明
---|---|---|---
modularId | 是 | Integer| 模块ID
modularName | 是 | String| 模块名称
submoduleId | 是 | Integer| 子模块名称
submoduleName | 是 | String| 子模块名称
fieldId | 是 | Integer| 字段ID
chName | 是 | String| 中文字段名称
enName | 是 | String| 英文字段名称
fieldType | 是 | Integer| 字段类型
value | 是 | String| 字段值 fieldType=3时为字段选项id
fieldValId | 是 | Integer| 字段选项ID
fieldVal | 是 | Integer| 字段选项值

sample:
```json
  "list": [
    {
	"modularId": 21,
	"modularName": "基本信息",
	"submoduleList": [{
				"submoduleId": 9,
				"submoduleName": "个人信息",
				"fieldList": [{
							"fieldId": 5,
							"chName": "婚姻状态",
							"enName": "hyzt",
							"fieldType": 3,
							"value": "",
							"fieldVal": [{
									"fieldValId": 26,
									"fieldVal": "已婚"
								},
								{
									"fieldValId": 27,
									"fieldVal": "未婚"
								}
							]
						}
    ]
```
------
#### 3.4 判断用户是不是会员
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/memberYxsj/isMemberUser.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>判断用户是不是会员</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
token | 是 | String| 用户token

##### data出参

参数名|非空|类型|说明
---|---|---|---
flag | 是 | Integer| 是否是会员 1:不是 2:是

sample:
```json
"data": {
   flag:1
}
```
------
#### 3.5会员基础列表(开通前页面)
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/memberYxsj/queryMemberBasicsList.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>会员基础列表(开通前页面)</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
token | 是 | String| 用户token

##### data出参

参数名|非空|类型|说明
---|---|---|---
memberBasicsId | 是 | Integer| 会员类型ID
memberBasicsName | 是 | Integer| 会员类型名称
avg | 是 | string| 日均
currentPrice | 是 | string| 现价
originalPrice | 是 | string| 原价
savePrice | 是 | string| 预计一年节省
rightsName | 是 | string| 权益名称
rightsType | 是 | Integer| 权益类型 1:次数 2:时长
bightsId | 是 | Integer| 权益ID
bightsOriginalPrice | 是 | string| 权益原价
bightsMemberPrice | 是 | string| 会员价
bightsPicUrl | 是 | string| 权益图标

sample:
```json
{
    "code": 0,
    "message": "成功",
    "data": {
        "list": [
            {
                "memberBasicsId": 1,
                "memberBasicsName": "黄金会员",
                "avg": "1",
                "currentPrice": "100",
                "originalPrice": "200",
                "savePrice": 1200.0,
                "tq1": [
                    {
                        "rightsName": "黑名单检测次数",
                        "rightsType": 1,
                        "bightsId": 1,
                        "bightsOriginalPrice": "29.9",
                        "bightsMemberPrice": "0.00",
                        "bightsPicUrl": "111"
                    },
                    {
                        "rightsName": "多头",
                        "rightsType": 1,
                        "bightsId": 2,
                        "bightsOriginalPrice": "39.9",
                        "bightsMemberPrice": "0.00",
                        "bightsPicUrl": "111"
                    }
                ],
                "tq2": []
            }
                ],
            }
        ]
    },
    "timestamp": 1594001197150
}
```
------
#### 3.6 购买页面
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/memberYxsj/purchase.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>购买页面</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
token | 是 | String| 用户token

##### data出参

参数名|非空|类型|说明
---|---|---|---
memberBasicsId | 是 | Integer| 会员类型ID
memberBasicsName | 是 | Integer| 会员类型名称
avg | 是 | string| 日均
currentPrice | 是 | string| 现价
originalPrice | 是 | string| 原价
hydj | 是 | string| 会员等级
qysc | 是 | Integer| 会员时间
hmdjc | 是 | Integer| 黑名单检测次数
dtjdjc | 是 | Integer| 多头拒贷检测次数

sample:
```json
{
    "code": 0,
    "message": "成功",
    "data": {
        "memberBasicsList": [
            {
                "memberBasicsId": 1,
                "memberBasicsName": "黄金会员",
                "avg": "1",
                "currentPrice": "100",
                "originalPrice": "200"
            },
            {
                "memberBasicsId": 2,
                "memberBasicsName": "铂金会员",
                "avg": "2",
                "currentPrice": "200",
                "originalPrice": "400"
            },
            {
                "memberBasicsId": 3,
                "memberBasicsName": "黑钻会员",
                "avg": "3",
                "currentPrice": "500",
                "originalPrice": "1000"
            }
        ],
        "rightsList": [
            {
                "hydj": "黄金会员",
                "qysc": 1,
                "hmdjc": 3,
                "dtjdjc": 3
            },
            {
                "hydj": "铂金会员",
                "qysc": 3,
                "hmdjc": 6,
                "dtjdjc": 6
            },
            {
                "hydj": "黑钻会员",
                "qysc": 6,
                "hmdjc": 12,
                "dtjdjc": 12
            }
        ]
    },
    "timestamp": 1594001903574
}
```
------
#### 3.7 支付接口
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/memberYxsj/aliPay.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>支付接口</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
token | 是 | String| 用户token
memberBasicsId | 是 | Integer| 会员类型Id
type | 是 | Integer|1:购买会员 2:单次查询报告
##### data出参

参数名|非空|类型|说明
---|---|---|---
pay | 是 | String| 支付宝返回的


sample:
```json
{
    "code": 0,
    "message": "成功",
    "data": {
        "pay":"===-==1221sdsdssdsd"
    },
    "timestamp": 1594001903574
}
```
------
#### 3.8 查看是否实名认证
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/memberYxsj/isUserCertification.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>查看是否实名认证</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
token | 是 | String| 用户token
##### data出参

参数名|非空|类型|说明
---|---|---|---
flag | 是 | Integer| 是否进行过实名认证 0:未认证 1:已认证


sample:
```json
{
    "code": 0,
    "message": "成功",
    "data": {
        "flag": 0
    },
    "timestamp": 1594002497352
}
```
------
------
#### 3.9 实名认证接口
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/UserPortrait/saveUserCertification.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>实名认证接口</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
token | 是 | String| 用户token
mobile | 是 | String| 用户手机号
idcard | 是 | String| 用户身份证号
name | 是 | String| 用户姓名

##### data出参
参数名|非空|类型|说明
无




sample:
```json
{
    "code": 0,
    "message": "成功",
    "data": {
    },
    "timestamp": 1594002497352
}
```
------

#### 4.0会员信息(开通后页面)
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/UserPortrait/memberInfo.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>会员信息(开通后页面)</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
token | 是 | String| 用户token


##### data出参
参数名|非空|类型|说明
endTime | 是 | String| 会员结束时间
memberBasicsName | 是 | String| 会员类型名称
phone | 是 | String| 用户实名手机号
memberNo | 是 | String| 会员编号
rightsName | 是 | string| 权益名称
rightsType | 是 | Integer| 权益类型 1:次数 2:时长
bightsId | 是 | Integer| 权益ID
bightsOriginalPrice | 是 | string| 权益原价
bightsMemberPrice | 是 | string| 会员价
bightsPicUrl | 是 | string| 权益图标

sample:
```json
{
    "code": 0,
    "message": "成功",
    "data": {
        "memberUserInfo": {
            "endTime": "2020-10-06",
            "memberBasicsName": "黄金会员",
            "phone": "18853153523",
            "memberNo": "NO.01.001"
        },
        "rightsList": [
            {
                "rightsName": "黑名单检测次数",
                "rightsType": 1,
                "bightsId": 1,
                "bightsOriginalPrice": "29.9",
                "bightsMemberPrice": "0.00",
                "bightsPicUrl": "111"
            },
            {
                "rightsName": "多头",
                "rightsType": 1,
                "bightsId": 2,
                "bightsOriginalPrice": "39.9",
                "bightsMemberPrice": "0.00",
                "bightsPicUrl": "111"
            }
        ]
    },
    "timestamp": 1594004628666
}
```
------
#### 4.1 查询检测报告
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/memberYxsj/queryRightsLog.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>查询检测报告</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
token | 是 | String| 用户token


##### data出参
参数名|非空|类型|说明
rightLog | 是 | String| 查询内容
createTime | 是 | String| 创建时间
rightsId | 是 | Integer| 1:黑名单 2:多头

sample:
```json

```
------
#### 4.2 查询实名认证信息
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/UserPortrait/queryUserCertificationInfo.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>查询实名认证信息</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
token | 是 | String| 用户token


##### data出参
参数名|非空|类型|说明
flag | 是 | Integer| 1:已认证  2:未认证
name | 是 | String| 姓名
idCard | 是 | String| 身份证号
mobile | 是 | String| 手机号
id | 是 | Integer| 实名认证信息主键

sample:
```json

```
------
### 4.桔子API接口

#### 4.1 身份证正反面上传
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/jz/upload.htmlt</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>用户上传身份证正反面照片</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
MultipartFile | 是 | file| 正反面照片

##### data出参

参数名|非空|类型|说明
---|---|---|---
imgUrl | 是 | String| 图标地址
content | 是 | String| 内容
sample:
```json
  "data": [
      {
        "content": "会员包下款",
        "imgUrl": "http://hyj-pro.oss-cn-shenzhen.aliyuncs.com//banner/img/1546597345872.jpg"
      },
      {
        "content": "会员包下款",
        "imgUrl": "http://hyj-pro.oss-cn-shenzhen.aliyuncs.com//banner/img/1546597345872.jpg"
      }
    ]
```
------
#### 4.2 保存身份认证信息
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/jz/saveIdentityAuthentication.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>查询检测报告</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
name | 是 | String| 姓名
idCardNum | 是 | String| 用户身份证号
idCardPositiveUrl | 是 | String| 身份证正面照片
idCardBackUrl | 是 | String| 身份证反面照片
address | 是 | String| 户籍地址
validTime | 是 | String| 身份证有效期
ethnicity | 是 | String| 民族
birthday | 是 | String| 出生年月
signingOrganization | 是 | String| 签证机关
accurate | 是 | String| GPS定位的详细地址
cityName | 是 | String| GPS定位的城市名称
latitude | 是 | String| GPS定位的纬度
longitude | 是 | String| GPS定位的经度
logincode | 是 | String| 设备码
livingImage1 | 是 | String| 活体照片1
livingImage2 | 是 | String| 活体照片2
sex | 是 | int| 性别 0女  1男

##### data出参
参数名|非空|类型|说明
无

------
#### 4.3 产品详情
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/jz/queryProductInfo.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>产品详情</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
productId | 是 | int| 产品Id

##### data出参
参数名|非空|类型|说明
---|---|---|---
name | 是 | string| 产品名称
productId | 是 | int| 产品Id
imgUrl | 是 | string| logo
adver | 是 | string| 广告语
moneyMax | 是 | string| 最大金额
moneyMin | 是 | string| 最小金额
rateMin | 是 | string| 最低利率
loanNum | 是 | string| 下款人数
dayMax | 是 | string| 最长期限
loanTime | 是 | string| 下款时间单位分钟
gongsiName | 是 | string| 公司名称
------
#### 4.4 查询身份认证信息
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/jz/queryUserIdCard.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>查询身份认证信息</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
无

##### data出参
参数名|非空|类型|说明
---|---|---|---
flag | 是 | int| 是否已认证 1:已认证 2:未认证
info | 是 | json| flag=1时,此字段存在
name | 是 | string| 姓名
idCardNum | 是 | string| 身份证号
sample:
```json
{
    "code": 0,
    "message": "成功",
    "data": {
        "flag":2,
        "info": {
            "name": "张三",
            "idCardNum": "31000000000000"
        }
    },
    "timestamp": 1594004628666
}
```
------
#### 4.5 渠道用户注册
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/jz/submitUserBaseInfo.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>渠道用户注册</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
productId | 是 | int| 产品Id
applyPrice | 是 | int| 申请金额
applyTerm | 是 | int| 申请期限
gpsLng | 是 | string| GPS定位的经度
gpsLat | 是 | string| GPS定位的纬度
gpsAddress | 是 | string| GPS定位的详细地址
gpsProvince | 是 | string| GPS定位的省名称
gpsCity | 是 | string| GPS定位的城市名称
gpsDistrict | 是 | string| GPS定位的县名称
logincode | 是 | string| 设备码

##### data出参
参数名|非空|类型|说明
---|---|---|---
无
------
------
#### 4.6 用户准入接口
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/jz/qualifyMd5.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>用户准入接口(用户提交用户资料是第一个调用的接口)</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
无

##### data出参
参数名|非空|类型|说明
---|---|---|---
isPass | 是 | boolean| true:允许准入 false:禁止准入
reason | 是 | string| 审核备注信息
```json
{
    "code": 0,
    "message": "成功",
    "timestamp": 1594004628666,
    "data":{
      "isPass":false,
      "reason":"您不符合申请条件，请在产品管理申请其他产品"
    }
}
```
------
#### 4.7 查询默认绑卡接口
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/jz/getDefaultCard.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>查询默认绑卡接口</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
orderNo | 是 | string| 订单编号

##### data出参
参数名|非空|类型|说明
---|---|---|---
cardNo | 是 | string| 银行卡号
isDefault | 是 | string| 是否默认绑卡 N否Y是
bankName | 是 | string| 银行名称
```json
{
    "code": 0,
    "message": "成功",
    "timestamp": 1594004628666
    "data":{
      "cardNo":"6214830175652357",
      "isDefault":"Y",
      "bankName":"中国工商银行"
    }
}
```
------
#### 4.8 查询订单列表
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/jz/queryOrderList.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>查询订单列表</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
flag | 是 | int| 订单状态 100:查询全部  0:审核中 4:带提现 5:待还款 6:已还款

##### data出参
参数名|非空|类型|说明
---|---|---|---
productName | 是 | string| 产品名称
applyTerm | 是 | int| 申请期限
applyPrice | 是 | int| 申请金额
status | 是 | int| 订单状态  0:审核中 1:审核失败 3:可重提 4:带提现
orderNo | 是 | string| 订单编号
```json
{
	"code": 0,
	"message": "成功",
	"data": {
		"list": [{
			"productName": "民生银行-助粒贷",
			"applyTerm": 12,
			"applyPrice": 50000,
			"status": 0,
			"id": 17
		}]
	},
	"timestamp": 1596456152489
}
```
------
#### 4.9 接收绑卡验证码接口
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/jz/confirmBindCard.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>接收绑卡验证码接口(点击提交绑卡触发)</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
orderNo | 是 | string| 订单编号
serialNumber | 是 | string| 交易流水号
verifyCode | 是 | string| 验证码

##### data出参
参数名|非空|类型|说明
---|---|---|---
无
------
#### 5.0 用户银行卡绑卡接口
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/jz/bindCard.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>提交用户银行卡信息,桔子系统发送验证码给手机号(绑卡第一步操作)</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
amount | 是 | int| 借款金额
certNo | 是 | string| 身份证号
cardNo | 是 | string| 银行卡号
phoneNumber | 是 | string| 预留手机号
orderNo | 是 | string| 订单编号
period | 是 | int| 分期期数
period | 是 | int| 分期期数
##### data出参
参数名|非空|类型|说明
---|---|---|---
serialNumber | 是 | string| 交易流水号(接口绑卡成功返回)
```json
{
	"code": 0,
	"message": "成功",
	"data": {
		"serialNumber": "A18032318385232938997"
	},
	"timestamp": 1596456152489
}
```
------
#### 5.1 查询用户额度
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/jz/queryAccountByChannelUid.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>查询用户额度</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
orderNo | 是 | string| 订单编号
##### data出参
参数名|非空|类型|说明
---|---|---|---
createTime | 是 | string| 开户日期
hasUserAmount | 是 | boolean| 激活状态 true 正常，false 冻结
totalAmount | 是 | string | 总授信额度
userAmount | 是 | string| 可用额度
```json
{
	"code": 0,
	"message": "成功",
	"data": {
		"createTime": "2020-09-09 10:00:00",
    "hasUserAmount": true,
    "totalAmount": "20000",
    "userAmount": "10000",
	},
	"timestamp": 1596456152489
}
```
------
#### 5.2 分期试算
<table>
  <tbody>
    <tr>
      <td>URI</td>
      <td>/jz/bigTrial.html</td>
    </tr>
    <tr>
      <td>描述</td>
      <td>分期试算</td>
    </tr>
  </tbody>
</table>

##### 入参
参数名|非空|类型|说明
---|---|---|---
orderNo | 是 | string| 订单编号
itemPrice | 是 | int| 试算金额
applyTerm | 是 | int| 分期期数
##### data出参
参数名|非空|类型|说明
---|---|---|---
applyTerm | 是 | int| 分期期数
interest | 是 | string| 月利息
period | 是 | int | 月期数
principal | 是 | string| 月本金
repayDay | 是 | string| 本期还款日
repayMoney | 是 | string| 本期总还
```json
{
	"code": 0,
	"message": "成功",
	"data": {
		"applyTerm": 12,
    "interest": 30.00,
		"period": 1,
		"principal": 323.53,
		"repayDay": "2019-11-18",
	  "repayMoney": 353.53
	},
	"timestamp": 1596456152489
}
```
------
