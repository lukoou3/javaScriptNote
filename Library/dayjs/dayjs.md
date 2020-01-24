## dayjs
dayjs是一个轻量的处理时间和日期的 JavaScript 库，这里是dayjs的github网址`https://github.com/iamkun/dayjs`。

dayjs好处

🕒 和Moment.js有着相同的API和模式
💪 不可变、持久性
🔥 提供链式调用
🌐 国际化标准
📦 超小的压缩体积，仅仅有2kb左右
👫 极大多数的浏览器兼容

Dayjs 并没有改变或覆盖 Javascript 原生的 Date.prototype， 而是创造了一个全新的包含 Javascript Date 对象的 Dayjs 的对象。

Dayjs 对象是不可变的, 所有的 API 操作都将返回一个新的 Dayjs 对象。

API中文文档`https://github.com/iamkun/dayjs/blob/master/docs/zh-cn/API-reference.md`
### dayjs安装
NPM:
```js
npm install dayjs --save

var dayjs = require('dayjs');
dayjs().format();
```

CDN:
```js
<script src="https://unpkg.com/dayjs"></script>
<script>
  dayjs().format();
</script>
```

### dayjs 解析相关的API
直接运行 dayjs()，得到包含当前时间和日期的 Dayjs 对象
```js
dayjs()  //返回当前时间 Tue, 28 May 2019 05:57:34 GMT
```

可以解析传入的一个标准的ISO 8601时间字符串。
```js
dayjs('1995-12-25') //Sun, 24 Dec 1995 16:00:00 GMT
```

可以解析传入的一个 Javascript Date 对象。
```js
dayjs(new Date(2018, 8, 18)) //Mon, 17 Sep 2018 16:00:00 GMT
```

可以解析传入的一个 时间戳 (毫秒) (13 位数字)。
```js
dayjs(1318781876406) //Sun, 16 Oct 2011 16:17:56 GMT
```

可以解析传入的一个 Unix 时间戳 (秒) (10 位数字)。
```js
dayjs.unix(1318781876) //Sun, 16 Oct 2011 16:17:56 GMT
```

Dayjs 对象是不可变的，如果您想获得一个对象的拷贝，请执行 .clone()。 向 dayjs() 里传入一个 Dayjs 对象也能实现同样的效果。
```js
dayjs(Dayjs)
dayjs().clone()
```

解析自定义时间格式如 
```js
dayjs("12-25-1995", "MM-DD-YYYY") 
```

检测当前 Dayjs 对象是否是一个有效的时间
```js
dayjs().isValid()
```

### dayjs 获取和设置相关的API
获取或设置年份。
```js
dayjs().year() //2019
dayjs().year(2000) //Sun, 28 May 2000 06:14:07 GMT
```

获取或设置月份。从 0 开始
```js
dayjs().month() //4 实际上5月
dayjs().month(0) //Mon, 28 Jan 2019 06:15:25 GMT
```

获取或设置日期。从 1 开始
```js
dayjs().date() //28 当天是2019年5月28日
dayjs().date(1) //Wed, 01 May 2019 06:17:04 GMT
```

获取或设置星期。从星期天 0 开始
```js
dayjs().day() //2 当天是星期二
dayjs().day(0) //Sun, 26 May 2019 06:18:13 GMT 被强行设置为上周日
```

获取或设置小时
```js
dayjs().hour()  //14 当时为下午2点
dayjs().hour(12) //Tue, 28 May 2019 04:21:30 GMT 不清楚
```

获取或设置分钟。
```js
dayjs().minute() //22 
dayjs().minute(59) //Tue, 28 May 2019 06:59:50 GMT
```

获取或设置秒
```js
dayjs().second()
dayjs().second(1)
```

获取或设置毫秒。
```js
dayjs().millisecond()
dayjs().millisecond(1)
```

获取从 Dayjs 对象中取到的信息 传入的单位 (unit) 对大小写不敏感
```js
dayjs().get('month') //4
```

设置时间
```js
dayjs().set('date', 1);
dayjs().set('month', 3); // 四月
dayjs().set('second', 30);
```

可用单位

| 单位          | 缩写 | 描述                        |
| ------------- | ---- | --------------------------- |
| `date`        |      | 日期                        |
| `day`         | `d`  | 星期几 (星期天 0, 星期六 6) |
| `month`       | `M`  | 月 (一月 0, 十二月 11)      |
| `year`        | `y`  | 年                          |
| `hour`        | `h`  | 时                          |
| `minute`      | `m`  | 分                          |
| `second`      | `s`  | 秒                          |
| `millisecond` | `ms` | 毫秒                        |

### dayjs 操作相关API
您可以对 Dayjs 对象如下增加减少之类的操作

增加时间并返回一个新的 Dayjs() 对象。
```js
dayjs().add(value : Number, unit : String);
dayjs().add(7, 'day'); //在当前的基础上加7天
```

减少时间并返回一个新的 Dayjs() 对象。
```js
dayjs().subtract(value : Number, unit : String);
dayjs().subtract(7, 'day'); //在当前基础上减少7天
```

返回当前时间的开头时间的 Dayjs() 对象，如月份的第一天。
```js
dayjs().startOf(unit : String);
dayjs().startOf('month'); //Tue, 30 Apr 2019 16:00:00 GMT 
```

返回当前时间的末尾时间的 Dayjs() 对象，如月份的最后一天。
```js
dayjs().endOf(unit : String);
dayjs().endOf('month'); //Fri, 31 May 2019 15:59:59 GMT
```

### 显示相关的API
格式化 Dayjs 对象并展示。

接收一系列的时间日期字符串并替换成相应的值。
```js
dayjs().format(String)
dayjs('2019-01-25').format('YYYY-MM-DD HH:mm:ss') 
dayjs().format('YYYY-MM-DD') 
dayjs().format('YYYY-MM') //2019
```

详情如下:

| 格式   | 输出             | 描述                         |
| ------ | ---------------- | ---------------------------- |
| `YY`   | 18               | 两位数的年份                 |
| `YYYY` | 2018             | 四位数的年份                 |
| `M`    | 1-12             | 月份，从 1 开始              |
| `MM`   | 01-12            | 月份，两位数                 |
| `MMM`  | Jan-Dec          | 简写的月份名称               |
| `MMMM` | January-December | 完整的月份名称               |
| `D`    | 1-31             | 月份里的一天                 |
| `DD`   | 01-31            | 月份里的一天，两位数         |
| `d`    | 0-6              | 一周中的一天，星期天是 0     |
| `dd`   | Su-Sa            | 最简写的一周中一天的名称     |
| `ddd`  | Sun-Sat          | 简写的一周中一天的名称       |
| `dddd` | Sunday-Saturday  | 一周中一天的名称             |
| `H`    | 0-23             | 小时                         |
| `HH`   | 00-23            | 小时，两位数                 |
| `h`    | 1-12             | 小时, 12 小时制              |
| `hh`   | 01-12            | Hours, 12 小时制, 两位数     |
| `m`    | 0-59             | 分钟                         |
| `mm`   | 00-59            | 分钟，两位数                 |
| `s`    | 0-59             | 秒                           |
| `ss`   | 00-59            | 秒 两位数                    |
| `SSS`  | 000-999          | 毫秒 三位数                  |
| `Z`    | +05:00           | UTC 的偏移量                 |
| `ZZ`   | +0500            | UTC 的偏移量，数字前面加上 0 |
| `A`    | AM PM            |                              |
| `a`    | am pm            |                              |

获取两个 Dayjs 对象的时间差，默认毫秒。
```js
const date1 = dayjs('2019-01-25')
const date2 = dayjs('2018-06-05')
date1.diff(date2) // 20214000000
date1.diff(date2, 'month') // 7
date1.diff(date2, 'month', true) // 7.645161290322581
date1.diff(date2, 'day') // 233
```

返回 Unix 时间戳 (毫秒)
```js
dayjs().valueOf()
```

返回 Unix 时间戳 (秒)。
```js
dayjs().unix()
```

返回月份的天数
```js
dayjs().daysInMonth()
```

返回原生的 Date 对象。
```js
dayjs().toDate()
```

当序列化 Dayjs 对象时，会返回 ISO8601 格式的字符串。
```js
dayjs().toJSON() //"2018-08-08T00:00:00.000Z"
```

返回 ISO8601 格式的字符串。
```js
dayjs().toISOString()
```

返回字符串
```js
dayjs().toString()
```

### 查询相关的API
检查一个 Dayjs 对象是否在另一个 Dayjs 对象时间之前。
```js
dayjs().isBefore(Dayjs, unit? : String);
dayjs().isBefore(dayjs()); // false
dayjs().isBefore(dayjs(), 'year'); // false
```

检查一个 Dayjs 对象是否和另一个 Dayjs 对象时间相同。
```js
dayjs().isSame(Dayjs, unit? : String);
dayjs().isSame(dayjs()); // true
dayjs().isSame(dayjs(), 'year'); // true
```

检查一个 Dayjs 对象是否在另一个 Dayjs 对象时间之后。
```js
dayjs().isAfter(Dayjs, unit? : String);
dayjs().isAfter(dayjs()); // false
dayjs().isAfter(dayjs(), 'year'); // false
```








