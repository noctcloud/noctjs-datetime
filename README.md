# NOCTJS-DATETIME

noctjs云函数dateTime模块，主要作用为日期时间处理。

### dateTime 日期时间操作
#### now(formatString, timezone)
获取当前时间

|参数|类型|必填|说明|
|--	|--	|--	|--	|
|formatString|String|否|日期格式化，`yyyy`表示年份，`MM`表示月份，`dd`表示日期，`HH`表示时，`mm`表示分，`ss`表示秒，`fff`表示毫秒。不填则返回为时间戳|
|timezone|Number|否|formatString存在时有效，格式化为指定时区的时间，默认8|

#### format(timestamp, formatString, timezone)
日期格式化

|参数|类型|必填|说明|
|--	|--	|--	|--	|
|timestamp|Number/String|是|要格式化的时间戳|
|formatString|String|是|日期格式化，`yyyy`表示年份，`MM`表示月份，`dd`表示日期，`HH`表示时，`mm`表示分，`ss`表示秒，`fff`表示毫秒|
|timezone|Number|否|时区，默认8|

#### addYears(timestamp, value)
添加年份

|参数|类型|必填|说明|
|--	|--	|--	|--	|
|timestamp|Number/String|是|时间戳|
|value|Number|是|要添加的年份数值|

#### addMonths(timestamp, value)
添加月份

|参数|类型|必填|说明|
|--	|--	|--	|--	|
|timestamp|Number/String|是|时间戳|
|value|Number|是|要添加的月份数值|

#### addDays(timestamp, value)
添加日期

|参数|类型|必填|说明|
|--	|--	|--	|--	|
|timestamp|Number/String|是|时间戳|
|value|Number|是|要添加的日期数值|

#### addHours(timestamp, value)
添加时

|参数|类型|必填|说明|
|--	|--	|--	|--	|
|timestamp|Number/String|是|时间戳|
|value|Number|是|要添加的时数值|

#### addMinutes(timestamp, value)
添加分

|参数|类型|必填|说明|
|--	|--	|--	|--	|
|timestamp|Number/String|是|时间戳|
|value|Number|是|要添加的分数值|

#### addSeconds(timestamp, value)
添加秒

|参数|类型|必填|说明|
|--	|--	|--	|--	|
|timestamp|Number/String|是|时间戳|
|value|Number|是|要添加的秒数值|

#### addMilliseconds(timestamp, value)
添加毫秒

|参数|类型|必填|说明|
|--	|--	|--	|--	|
|timestamp|Number/String|是|时间戳|
|value|Number|是|要添加的毫秒数值|

#### 使用示例
```javascript
const dateTime = require("noctjs-datetime");

dateTime.now("yyyy-MM-dd HH:mm:ss"); // 得到格式为2020-11-11 00:00:00的当前时间
dateTime.format(1605024000000, "yyyy年MM月dd日HH时mm分ss秒"); // 格式化时间为2020年11月11日00时00分00秒
dateTime.addYears(1605024000000, 2); // 原始日期为2020年11月11日，年份增加2年，结果为2022年11月11日
dateTime.addMonths(1605024000000, 13); // 原始日期为2020年11月，增加13个月，结果为2021年12月
dateTime.addHours(1605024000000, -1); // 原始日期为2020年11月11日00时，增加-1时，结果为2020年11月10日23时
```