# 事件（Event）

在Apache OFBiz 中，事件是一些用来和HttpServletRequest与HttpServletResponse对象一起工作的简单方法，事件是通过controller直接调用的，当你想要为输入参数添加自定义的服务端验证时，时间会比较有用。当进行数据库操作时，你仍然可以在事件中调用内置的服务。

在 **framework\common\webcommon\WEB-INF\handlers-controller.xml** 文件中可以找到所有支持的事件类型

```
<!-- event handlers -->
<handler name="java" type="request" class="org.ofbiz.webapp.event.JavaEventHandler"/>
<handler name="soap" type="request" class="org.ofbiz.webapp.event.SOAPEventHandler"/>
<handler name="xmlrpc" type="request" class="org.ofbiz.webapp.event.XmlRpcEventHandler"/>
<handler name="service" type="request" class="org.ofbiz.webapp.event.ServiceEventHandler"/>
<handler name="service-multi" type="request" class="org.ofbiz.webapp.event.ServiceMultiEventHandler"/>
<handler name="service-stream" type="request" class="org.ofbiz.webapp.event.ServiceStreamHandler"/>
<handler name="simple" type="request" class="org.ofbiz.webapp.event.SimpleEventHandler"/>
<handler name="groovy" type="request" class="org.ofbiz.webapp.event.GroovyEventHandler"/>
<handler name="rome" type="request" class="org.ofbiz.webapp.event.RomeEventHandler"/>
<handler name="script" type="request" class="org.ofbiz.webapp.event.ScriptEventHandler"/>    
```

