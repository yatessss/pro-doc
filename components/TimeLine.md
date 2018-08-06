# TimeLine

## 使用

首先引入组件：

```js
import {WeTimeline} from 'apps/webankPro/bizComponents'

<WeTimeline data={{
  type: PropTypes.oneOf([TYPE.CLOSED, TYPE.NOT_CLOSE]), // 时间轴分为：封闭 非封闭 默认封闭
  style: ViewPropTypes.style, // 附加style
  title: PropTypes.string, // 标题
  items: PropTypes.arrayOf(PropTypes.shape({
    label: PropTypes.string.isRequired, // 文字
    date: PropTypes.string.isRequired, // 日期传入 YYYYMMDD格式
    percentage: PropTypes.number, // 所占百分比 可不传默认平分
    light: PropTypes.bool // 文字和日期变成橘色
  })),
  remark: PropTypes.shape({
    startPercentage: PropTypes.number,
    endPercentage: PropTypes.number,
    label: PropTypes.string
  }),  // 时间轴描述项
  otherElement: PropTypes.element // 时间轴下方文案展示  传入一段要渲染的内容
}} />
```

## 参数

参数名 | 说明 | 是否必要 | 类型 | 默认值
---- | ---
type | 时间轴类型，有[TimeLine.CLOSED, TimeLine.NOT_CLOSE] | 否 | string | TimeLine.CLOSED
style |  时间轴容器的样式 | 否 | style | 
title |  时间轴title | 否 | string | 产品周期
items |  时间轴数据 | 是 | array | 
items.label |  时间轴文字 | 是 | string | 
items.date |  日期传入 | 是 | YYYYMMDD | 
items.percentage |  所占百分比 | 否 | number | 平分时间轴
items.light |  文字和日期变成橘色 | 否 | boolean | false
remark |  时间轴下方描述 | 否 | object | 
remark.startPercentage |  开始位置 | 是 | number | 
remark.endPercentage |  结束位置 | 是 | number | 
remark.label |  描述 | 是 | boolean | false
otherElement |  时间轴下方渲染的内容 | 否 | element |

## 方法

##### atWhichStage （判断时间走到了什么位置）

>看传入的items长度是多少，比如长度是3：

>1---------2---------3

>在[1, 2)间返回1

>在[2, 3)间返回2

>在3返回3


## 效果图