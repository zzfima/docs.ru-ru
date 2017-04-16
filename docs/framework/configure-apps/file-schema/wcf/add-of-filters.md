---
title: "&lt;add&gt; для &lt;filters&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;add&gt; для &lt;filters&gt;
Фильтр XPath, задающий тип сообщений для записи в журнал.  
  
## Синтаксис  
  
```  
  
<filters>  
   <add filter="String"/>  
</filters>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|фильтр|Строка, задающая запрос к документу XML, определенный в виде выражения XPath 1.0.  Для получения дополнительной информации см. <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<фильтры\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters.md)|Содержит коллекцию фильтров XPath, используемых для контроля типов регистрируемых сообщений.|  
  
## Заметки  
 Фильтры применяются только на транспортном уровне, когда параметр `logMessagesAtTransportLevel` имеет значение `true`.  Фильтры не влияют на ведение журнала сообщений уровня службы и неправильно сформированных сообщений.  
  
 Для добавления нового фильтра в коллекцию используется ключевое слово `add`.  Если в файле конфигурации определены один или несколько фильтров, в журнал записываются только сообщения, соответствующие хотя бы одному из фильтров.  Если фильтры не заданы, в журнал записываются все сообщения.  
  
 Фильтры поддерживают полный синтаксис XPath и применяются в том порядке, в котором они записаны в файле конфигурации.  Синтаксически неверные фильтры вызывают исключения конфигурации.  
  
 В следующем примере показано, как настроить фильтр для записи только сообщений с разделом заголовка SOAP.  
  
## Пример  
 В следующем примере показано, как настроить фильтр для записи только сообщений с разделом заголовка SOAP.  
  
```  
<messageLogging logEntireMessage="true"  
     logMalformedMessages="true" logMessagesAtServiceLevel="true"  
     logMessagesAtTransportLevel="true" maxMessagesToLog="420”>  
     <filters>  
        <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">  
                        /soap:Envelope/soap:Headers  
        </add>  
     </filters>  
</messageLogging>  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>   
 <xref:System.ServiceModel.Diagnostics>   
 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>   
 <xref:System.ServiceModel.Configuration.MessageLoggingElement>   
 <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>   
 <xref:System.ServiceModel.Configuration.XpathMessageFilterElement>   
 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>   
 [Настройка ведения журнала сообщений](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)   
 [Настройка ведения журнала сообщений](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)   
 [\<messageLogging\>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)