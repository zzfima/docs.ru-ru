---
title: "&lt;фильтры&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37a87222-ec78-4728-8105-9ca1bd961f0c
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 21f2115f83772312e1b9f42a66c53ba8ee2834f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltfiltersgt"></a><span data-ttu-id="a188e-102">&lt;фильтры&gt;</span><span class="sxs-lookup"><span data-stu-id="a188e-102">&lt;filters&gt;</span></span>

<span data-ttu-id="a188e-103">Элемент `filters` содержит коллекцию фильтров XPath, используемых для отбора сообщений, записываемых в журнал.</span><span class="sxs-lookup"><span data-stu-id="a188e-103">The `filters` element holds a collection of XPath filters used to control what kind of message is logged.</span></span>

<span data-ttu-id="a188e-104">Фильтры применяются только на транспортном уровне, когда параметр `logMessagesAtTransportLevel` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="a188e-104">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="a188e-105">Фильтры не влияют на ведение журнала сообщений уровня службы и неправильно сформированных сообщений.</span><span class="sxs-lookup"><span data-stu-id="a188e-105">Service level and malformed message logging are not affected by filters.</span></span>

<span data-ttu-id="a188e-106">Для добавления нового фильтра в коллекцию используется ключевое слово `add`.</span><span class="sxs-lookup"><span data-stu-id="a188e-106">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="a188e-107">Если в файле конфигурации определены один или несколько фильтров, в журнал записываются только сообщения, соответствующие хотя бы одному из фильтров.</span><span class="sxs-lookup"><span data-stu-id="a188e-107">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="a188e-108">Если фильтры не заданы, в журнал записываются все сообщения.</span><span class="sxs-lookup"><span data-stu-id="a188e-108">If no filter is defined, all messages pass through.</span></span>

<span data-ttu-id="a188e-109">Фильтры поддерживают полный синтаксис XPath и применяются в том порядке, в котором они записаны в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a188e-109">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="a188e-110">Синтаксически неверные фильтры вызывают исключения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a188e-110">A syntactically incorrect filter results in a configuration exception.</span></span>

<span data-ttu-id="a188e-111">В следующем примере показано, как настроить фильтр для записи только сообщений с разделом заголовка SOAP.</span><span class="sxs-lookup"><span data-stu-id="a188e-111">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a188e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a188e-112">See also</span></span>

 <span data-ttu-id="a188e-113"><xref:System.ServiceModel.Configuration.DiagnosticSection><xref:System.ServiceModel.Diagnostics> <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> <xref:System.ServiceModel.Configuration.MessageLoggingElement> <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A> <xref:System.ServiceModel.Configuration.XPathMessageFilterElementCollection> <xref:System.ServiceModel.Configuration.XPathMessageFilterElement> <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> [Настройка ведения журнала сообщений](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) [ \<messageLogging >](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)</span><span class="sxs-lookup"><span data-stu-id="a188e-113"><xref:System.ServiceModel.Configuration.DiagnosticSection> <xref:System.ServiceModel.Diagnostics> <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> <xref:System.ServiceModel.Configuration.MessageLoggingElement> <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A> <xref:System.ServiceModel.Configuration.XPathMessageFilterElementCollection> <xref:System.ServiceModel.Configuration.XPathMessageFilterElement> <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> [Configuring Message Logging](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) [\<messageLogging>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)</span></span>
