# [快速获得数据](https://apistore.eolinker.com)
[快速获得数据](https://apistore.eolinker.com)
## 通过地名查询邮编
### 基本信息
接口地址：`http://apis.eolinker.com/common/postcode/getPostCodeByAddr`  
支持格式：`json`  
请求协议：`HTTP`  
请求方式：`GET、POST`  
请求示例：`http://apis.eolinker.com/common/postcode/getPostCodeByAddr?productKey=您的产品密钥&productKey=参数1&province=参数2&city=参数3&area=参数4&address=参数5&page=参数6&pageSize=参数7`
### 请求参数
| 参数名 |类型 | 必填 |	说明 |
| :- | :-: | :-: | :- |
| productKey  |	[text]	| 是 |申请接口后在接口列表查看 |
| province    |	[text]	| 否 |省份（省份、城市、区/县、地址关键字必须四选一输入）| 
| city	      | [text]	| 否 |城市（省份、城市、区/县、地址关键字必须四选一输入）|
| area	      | [text]	| 否 |区/县（省份、城市、区/县、地址关键字必须四选一输入）|
| address	  | [text]	| 否 |地名关键字，如“一路”（省份、城市、区/县、地址关键字必须四选一输入）|
| page	      | [text]	| 否 |页码，默认第一页 |
| pageSize	  | [text]	| 否 |每页条数，默认10条，最多40条 |

### 返回参数
| 参数名 |类型 | 必填 |	说明 |
| :- | :-: | :-: | :- |
| statusCode  |	[text]	| 是 | 状态码，包括系统级状态码以及接口状态码，详情参考状态码文档 |
| desc        |	[text]	| 是 | 状态码说明 |
| result      |	[text]	| 是 | 接口的返回信息，数组形式 |

### 返回结果示例
```{
    "statusCode":"000000",
    "desc":"请求成功",
    "result":{
        "itemCount":56,//总条数
        "pageNow":1//当前页码
        "postCodeList":[
            {
                "address":"大学城",//地址
                "area":"海珠区",//地区名
                "city":"广州市",//城市
                "postCode":"510006",//邮编
                "province":"广东省"//省份
            }
        ]
    }
}```


