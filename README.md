# OpenReading必须具备以下接口
## 章节获取接口
请求：/chapter/list
请求方式：GET

响应：["中国文学","外国文学","古籍精选","专业书籍","网文精选"]

## 书籍获取接口
请求：novel/list?page_no=1&&section=中国文学
请求方式：GET

响应：
[{"author":"鲁迅","del":0,"country":"中","id":1,"category":"中国文学","publish_year":"1921","cover":"\/9j\/4QAYRXhpZgAASUkqAAgAAAAAAAAAAAAAAP\/9k=","name":"狂人日记"}]

- cover字段为将图片使用BASE64算法加密后得到的字符串，建议图片大小不要超过5k，以免造成用户加载缓慢。

## 章节获取接口
请求：novel/chapter/detail?novel=1&chapter=1
请求方式：GET

响应：
[{"chapter_id":"1","section":"A","chapter_content":"文章主体","chapter_name":"序","is_last_chapter":"yes","is_first_chapter":"yes","novel_id":"1"}]

**注意**
1. chapter_id即为章节ID，从1开始计数，步长为1；
2. section可以为空
3. chapter_content只支持h1/h2/h3/h4/h5/h6/p/ul/ol/li/table/tr/td/b/li/img/blockquote标签。块级元素（如h1 h2 p）之间需要使用\n来分割，如</p>\n<p>，
