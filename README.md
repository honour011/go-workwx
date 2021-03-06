# go-workwx

[![Travis Build Status](https://img.shields.io/travis/xen0n/go-workwx.svg)](https://travis-ci.org/xen0n/go-workwx)
[![Go Report Card](https://goreportcard.com/badge/github.com/xen0n/go-workwx)](https://goreportcard.com/report/github.com/xen0n/go-workwx)
[![GoDoc](http://godoc.org/github.com/xen0n/go-workwx?status.svg)](http://godoc.org/github.com/xen0n/go-workwx)

```go
import (
    "github.com/xen0n/go-workwx" // package workwx
)
```

Yet another Work Weixin client for Golang

又一个 Golang 企业微信客户端


> English translation TODO for now, as the service covered here is not available
> outside of China (AFAIK).


## Why another wheel?

工作中需要用 Go 实现一个简单的消息推送，想着找个开源库算了，然而现有唯一的开源企业微信 Golang SDK 代码质量不佳。只好自己写一个。


## Features

* [x] access token 刷新
* [ ] 通讯录管理
* [ ] 外部联系人管理
* [ ] 应用管理
* [x] 消息发送 (**部分支持**，见下)
* [ ] 素材管理

<details>
<summary>通讯录管理 API</summary>

* [ ] 成员管理
    - [ ] 创建成员
    - [x] 读取成员 *NOTE: 成员对外信息暂未实现*
    - [ ] 更新成员
    - [ ] 删除成员
    - [ ] 批量删除成员
    - [ ] 获取部门成员
    - [ ] 获取部门成员详情
    - [ ] userid与openid互换
    - [ ] 二次验证
    - [ ] 邀请成员
* [ ] 部门管理
    - [ ] 创建部门
    - [ ] 更新部门
    - [ ] 删除部门
    - [ ] 获取部门列表
* [ ] 标签管理
    - [ ] 创建标签
    - [ ] 更新标签名字
    - [ ] 删除标签
    - [ ] 获取标签成员
    - [ ] 增加标签成员
    - [ ] 删除标签成员
    - [ ] 获取标签列表
* [ ] 异步批量接口
    - [ ] 增量更新成员
    - [ ] 全量覆盖成员
    - [ ] 全量覆盖部门
    - [ ] 获取异步任务结果
* [ ] 通讯录回调通知
    - [ ] 成员变更通知
    - [ ] 部门变更通知
    - [ ] 标签变更通知
    - [ ] 异步任务完成通知

</details>

<details>
<summary>外部联系人管理 API</summary>

* [ ] 离职成员的外部联系人再分配
* [ ] 成员对外信息
* [ ] 获取外部联系人详情

</details>

<details>
<summary>应用管理 API</summary>

* [ ] 获取应用
* [ ] 设置应用
* [ ] 自定义菜单
    - [ ] 创建菜单
    - [ ] 获取菜单
    - [ ] 删除菜单

</details>

<details>
<summary>消息发送 API</summary>

* [x] 发送应用消息
* [ ] 接收消息
* [x] 发送消息到群聊会话
    - [ ] 创建群聊会话
    - [ ] 修改群聊会话
    - [ ] 获取群聊会话
    - [x] 应用推送消息

### 消息类型

* [x] 文本消息
* [ ] 图片消息
* [ ] 语音消息
* [ ] 视频消息
* [ ] 文件消息
* [ ] 文本卡片消息
* [ ] 图文消息
* [ ] 图文消息（mpnews）
* [x] markdown消息

</details>

## Notes

### 关于保密消息发送

Markdown 等类型消息目前不支持作为保密消息发送，强行发送会报错。
那么为何发送消息的方法还全部带着 `isSafe` 参数呢？

一方面，企业微信服务方完全可能在未来支持更多消息类型的保密发送，到时候不希望客户端代码重新编译；
另一方面，反正响应会报错，你也不会留着这种逻辑。因此不改了。


## License

* [MIT](./LICENSE)
