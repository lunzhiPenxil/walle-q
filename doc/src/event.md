# 事件 Event

所有事件共有字段

| 字段     | 类型   | 说明                 |
| -------- | ------ | -------------------- |
| id       | String | 事件ID               |
| impl     | String | 实现名，即 `Walle-Q` |
| platform | String | 平台名，即 `qq`      |
| self_id  | String | Bot ID               |
| time     | f64    | 事件戳，单位：秒     |

## 消息事件 message

### 单用户消息事件 message.private

| 字段        | 类型    | 说明      |
| ----------- | ------- | --------- |
| message_id  | String  | 消息 ID   |
| message     | Message | 消息对象  |
| alt_message | String  | 消息文本  |
| user_id     | String  | 发送者 ID |

### 群用户消息事件 message.group

| 字段        | 类型    | 说明      |
| ----------- | ------- | --------- |
| message_id  | String  | 消息 ID   |
| message     | Message | 消息对象  |
| alt_message | String  | 消息文本  |
| user_id     | String  | 发送者 ID |
| group_id    | String  | 群 ID     |

## 通知事件 notice

### 好友消息撤回 notice.private_message_delete

| 字段       | 类型   | 说明      |
| ---------- | ------ | --------- |
| message_id | String | 消息 ID   |
| user_id    | String | 发送者 ID |

### 好友增加 notice.friend_increase

| 字段    | 类型   | 说明    |
| ------- | ------ | ------- |
| user_id | String | 好友 ID |

### 群成员增加 notice.group_member_increase

| 字段        | 类型   | 说明             |
| ----------- | ------ | ---------------- |
| sub_type    | String | 加群类型         |
| user_id     | String | 成员 ID          |
| group_id    | String | 群 ID            |
| operator_id | String | 操作者 ID (暂缺) |

### 群成员减少 notice.group_member_decrease

| 字段        | 类型   | 说明      |
| ----------- | ------ | --------- |
| sub_type    | String | 退群类型  |
| user_id     | String | 成员 ID   |
| group_id    | String | 群 ID     |
| operator_id | String | 操作者 ID |

### 群成员禁言 notice.group_member_ban

| 字段        | 类型   | 说明      |
| ----------- | ------ | --------- |
| user_id     | String | 成员 ID   |
| group_id    | String | 群 ID     |
| operator_id | String | 操作者 ID |

### 群消息撤回 notice.group_message_delete

| 字段        | 类型   | 说明                      |
| ----------- | ------ | ------------------------- |
| sub_type    | String | 撤回类型 recall 或 delete |
| message_id  | String | 消息 ID                   |
| user_id     | String | 成员 ID                   |
| group_id    | String | 群 ID                     |
| operator_id | String | 操作者 ID                 |

### 群管理员设置 notice.group_admin_set

| 字段        | 类型   | 说明      |
| ----------- | ------ | --------- |
| user_id     | String | 成员 ID   |
| group_id    | String | 群 ID     |
| operator_id | String | 操作者 ID |

### 群管理员取消 notice.group_admin_unset

| 字段        | 类型   | 说明      |
| ----------- | ------ | --------- |
| user_id     | String | 成员 ID   |
| group_id    | String | 群 ID     |
| operator_id | String | 操作者 ID |