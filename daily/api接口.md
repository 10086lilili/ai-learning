## api：中间人传话通道

请求方式:POST

请求参数

| 参数 | 类型 | 说明 |
|------|------|------|
| course | String | 课程名称 |
| knowledge_point | String | 知识点 |
| question_type | String | 题型 |
| difficulty | String | 难度 |
| count | Integer | 生成数量 

请求示例：

{
    "course":"数据结构",
    "knowledge_point":"AVL树",
    "question_type":"选择题",
    "difficulty":"中等",
    "count":5
}

---

返回结果

{
    "question":"",
    "options":[],
    "answer":"",
    "analysis":"",
    "difficulty":"",
    "knowledge_point":""
}
