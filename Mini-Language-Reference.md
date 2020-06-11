# 迷你语言参考引用

本章节主要介绍迷你语言一些元素的含义。

## 属性

### 属性类型介绍

|类型|描述|样例|
|----|----|----|
|常量|一个字符串常量，字符串可能不包含表达式|name="fooMethod"|
|常量+表达式|一个字符串常量，字符串可能包含一个表达式，但是一个只有表达式的字符串是不被允许的|default="${foo}Method"|
|表达式|一个没有封闭括号的UEL表达式 |from="item.quantity * item.priceEach"|
|${表达式}|一个带有封闭括号的UEL表达式|default="${parameters.itemId}"|
|脚本|一个简短的脚本|script="groovy:foo.bar();"|

## 元素说明

* simple-method

simple-method 包含一个代码块。

一个 simple method 既可以被Control Servlet或其他事件在事件上下文中调用，也可以被服务引擎在服务上下文中调用，还可以被任何可以获得 service dispatcher 的其他组件调用。

一个 simple method 代码块如下所示

```xml
<simple-method method-name="fooMethod">
  <!-- 这里可以编写一些迷你语言的代码 -->
</simple-method>
```

simple-method的属性列表如下

|属性名|类型|是否必须|描述|备注|
|-----|------|-------|----|----|
|method-name|常量|必填|方法的名字，最好是一个合法的Java识别码|每个文件中simple method的名字必须是唯一的|
|short-description|常量|选填|方法的简短介绍|用于文档注释|
|login-required|常量|选填|是否需要用户登录才能调用该方法|默认为"true"|
|use-transaction|常量|选填|如果该线程不存在则创建事务|默认为"true"|
|default-error-code|常量|选填|默认的错误返回码|默认为"error"|
|default-success-code|常量|选填|默认成功返回码|默认为"success"|
|event-request-object-name|常量|选填|包含 javax.servlet.ServletRequest 对象的成员变量名|默认为"request"|
|event-response-object-name|常量|选填|包含 javax.servlet.ServletResponse 对象的成员变量名|默认为"response"|
|event-session-object-name|常量|选填|包含 javax.servlet.http.HttpSession 对象的成员变量名|默认为"session"|
|event-response-code-name|常量|选填|包含事件响应码的成员变量名|默认为"_response_code_"|
|event-error-message-name|常量|选填|包含事件错误信息的成员变量名|默认为"_error_message_"|
|event-error-message-list-name|常量|选填|包含错误事件消息列表的成员变量名|默认为"_error_message_list_"|
|event-event-message-name|常量|选填|包含事件消息的成员变量名|默认为"_event_message_"|
|event-event-message-list-name|常量|选填|包含事件消息列表的成员变量名|默认为"_event_message_list_"|
|service-response-message-name|常量|选填|包含服务响应消息的成员变量名|默认为"responseMessage"|
|service-error-message-name|常量|选填|包含服务错误消息的成员变量名|默认为"errorMessage"|
|service-error-message-list-name|常量|选填|包含服务错误消息列表的成员变量名|默认为"errorMessageList"|
|service-error-message-map-name|常量|选填|包含服务错误消息map的成员变量名|默认为"errorMessageMap"|
|service-success-message-name|常量|选填|包含服务成功消息的成员变量名|默认为"successMessage"|
|service-success-message-list-name|常量|选填|包含服务成功消息列表的成员变量名|默认为"successMessageList"|

## 参考引用
1. https://cwiki.apache.org/confluence/display/OFBIZ/Mini+Language+-+minilang+-+simple-method+-+Reference
