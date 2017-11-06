# unity3d-windjson
* WindJson解析库中的词法分析算法采用词法状态转换矩阵算法，该算法的代码非常精简，将每个类别的单词分析高度抽象成为一个状态转换矩阵进行表示，同时将分析Json的词法和Json语法抽象成了两个层次，因此代码逻辑结构变得非常简单。

## WindJson支持的功能
* 支持标准的Json格式解析
* 方便的从object/jsonstring/jsonnode三者之间相互转化
* 兼容重复的逗号，分号
* 支持枚举类型、true/false关键字的识别
* 支持 // /**/ 注释的识别
* 支持ILRuntime热更新端使用该Json库，需要添加ILRUNTIME_USE宏
 
## WindJson的API
* jsonstring ==> jsonnode
```C#
JsonParser rJsonParser = new JsonParser(rText);
JsonNode rJsonNode = rJsonParser.Parser();
```
* jsonnode ==> object
```C#
var rObjet = rJsonNode.ToObject(rObjectType);
var rObjet1 = rJsonNode.ToObject<ObjectType>();			// To object

var rObjectList = rJsonNode.ToList<ObjectType>();		// To list

var rObjectDict = rJsonNode.ToDict<TKey, TObject>();	// To dictionary
```
* object ==> jsonnode
```C#
JsonNode rJsonNode = JsonParser.ToJsonNode(rObject);
```

* jsonnode ==> jsonstring
```C#
string rJsonString = rJsonNode.ToString();
```

## 测试用例
![JsonParser1](https://github.com/winddyhe/knight/blob/master/Doc/res/images/json_1.png)
![JsonParser1](https://github.com/winddyhe/knight/blob/master/Doc/res/images/json_2.png)
