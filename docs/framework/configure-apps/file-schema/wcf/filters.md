---
title: '&lt;Фильтры&gt;'
ms.date: 03/30/2017
ms.assetid: 37a87222-ec78-4728-8105-9ca1bd961f0c
ms.openlocfilehash: aae70fbe873eee10fcf95dcdd443dfa9ae6efb57
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148972"
---
# <a name="ltfiltersgt"></a>&lt;Фильтры&gt;

Элемент `filters` содержит коллекцию фильтров XPath, используемых для отбора сообщений, записываемых в журнал.

Фильтры применяются только на транспортном уровне, когда параметр `logMessagesAtTransportLevel` имеет значение `true`. Фильтры не влияют на ведение журнала сообщений уровня службы и неправильно сформированных сообщений.

Для добавления нового фильтра в коллекцию используется ключевое слово `add`. Если в файле конфигурации определены один или несколько фильтров, в журнал записываются только сообщения, соответствующие хотя бы одному из фильтров. Если фильтры не заданы, в журнал записываются все сообщения.

Фильтры поддерживают полный синтаксис XPath и применяются в том порядке, в котором они записаны в файле конфигурации. Синтаксически неверные фильтры вызывают исключения конфигурации.

В следующем примере показано, как настроить фильтр для записи только сообщений с разделом заголовка SOAP.
  
```xml  
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="420">
  <filters>
    <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
      /soap:Envelope/soap:Headers
    </add>
  </filters>
</messageLogging>
```  
  
## <a name="see-also"></a>См. также

 <xref:System.ServiceModel.Configuration.DiagnosticSection> <xref:System.ServiceModel.Diagnostics>
 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
 <xref:System.ServiceModel.Configuration.MessageLoggingElement>
 <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
 <xref:System.ServiceModel.Configuration.XPathMessageFilterElementCollection>
 <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
 [Настройка ведения журнала сообщений](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) [ \<messageLogging >](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)
