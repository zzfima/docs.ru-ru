---
title: <add> из <filters>
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: 280c516b17a133930bc4b6621a8c9bc7f4781085
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850561"
---
# <a name="add-of-filters"></a><span data-ttu-id="64eb7-102">\<Добавление > \<фильтров ></span><span class="sxs-lookup"><span data-stu-id="64eb7-102">\<add> of \<filters></span></span>
<span data-ttu-id="64eb7-103">Фильтр XPath, задающий тип сообщений для записи в журнал.</span><span class="sxs-lookup"><span data-stu-id="64eb7-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
<span data-ttu-id="64eb7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="64eb7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="64eb7-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="64eb7-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="64eb7-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Диагностика >** ](diagnostics.md)</span><span class="sxs-lookup"><span data-stu-id="64eb7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)</span></span>\
<span data-ttu-id="64eb7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Мессажелоггинг >** ](messagelogging.md)</span><span class="sxs-lookup"><span data-stu-id="64eb7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<messageLogging>**](messagelogging.md)</span></span>\
<span data-ttu-id="64eb7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Фильтры >** ](filters.md)</span><span class="sxs-lookup"><span data-stu-id="64eb7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters.md)</span></span>\
<span data-ttu-id="64eb7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="64eb7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64eb7-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64eb7-110">Syntax</span></span>  
  
```xml  
<filters>
  <add filter="String" />
</filters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64eb7-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="64eb7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="64eb7-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="64eb7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64eb7-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="64eb7-113">Attributes</span></span>  
  
|<span data-ttu-id="64eb7-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="64eb7-114">Attribute</span></span>|<span data-ttu-id="64eb7-115">Описание</span><span class="sxs-lookup"><span data-stu-id="64eb7-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="64eb7-116">фильтр</span><span class="sxs-lookup"><span data-stu-id="64eb7-116">filter</span></span>|<span data-ttu-id="64eb7-117">Строка, задающая запрос к документу XML, определенный в виде выражения XPath 1.0.</span><span class="sxs-lookup"><span data-stu-id="64eb7-117">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="64eb7-118">Дополнительные сведения см. в разделе <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="64eb7-118">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64eb7-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="64eb7-119">Child Elements</span></span>  
 <span data-ttu-id="64eb7-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="64eb7-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="64eb7-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="64eb7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="64eb7-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="64eb7-122">Element</span></span>|<span data-ttu-id="64eb7-123">Описание</span><span class="sxs-lookup"><span data-stu-id="64eb7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64eb7-124">\<Фильтры></span><span class="sxs-lookup"><span data-stu-id="64eb7-124">\<filters></span></span>](filters.md)|<span data-ttu-id="64eb7-125">Содержит коллекцию фильтров XPath, используемых для контроля типов регистрируемых сообщений.</span><span class="sxs-lookup"><span data-stu-id="64eb7-125">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64eb7-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="64eb7-126">Remarks</span></span>  
 <span data-ttu-id="64eb7-127">Фильтры применяются только на транспортном уровне, когда параметр `logMessagesAtTransportLevel` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="64eb7-127">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="64eb7-128">Фильтры не влияют на ведение журнала сообщений уровня службы и неправильно сформированных сообщений.</span><span class="sxs-lookup"><span data-stu-id="64eb7-128">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="64eb7-129">Для добавления нового фильтра в коллекцию используется ключевое слово `add`.</span><span class="sxs-lookup"><span data-stu-id="64eb7-129">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="64eb7-130">Если в файле конфигурации определены один или несколько фильтров, в журнал записываются только сообщения, соответствующие хотя бы одному из фильтров.</span><span class="sxs-lookup"><span data-stu-id="64eb7-130">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="64eb7-131">Если фильтры не заданы, в журнал записываются все сообщения.</span><span class="sxs-lookup"><span data-stu-id="64eb7-131">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="64eb7-132">Фильтры поддерживают полный синтаксис XPath и применяются в том порядке, в котором они записаны в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="64eb7-132">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="64eb7-133">Синтаксически неверные фильтры вызывают исключения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="64eb7-133">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="64eb7-134">В следующем примере показано, как настроить фильтр для записи только сообщений с разделом заголовка SOAP.</span><span class="sxs-lookup"><span data-stu-id="64eb7-134">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64eb7-135">Пример</span><span class="sxs-lookup"><span data-stu-id="64eb7-135">Example</span></span>  
 <span data-ttu-id="64eb7-136">В следующем примере показано, как настроить фильтр для записи только сообщений с разделом заголовка SOAP.</span><span class="sxs-lookup"><span data-stu-id="64eb7-136">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64eb7-137">См. также</span><span class="sxs-lookup"><span data-stu-id="64eb7-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="64eb7-138">Настройка ведения журналов сообщений</span><span class="sxs-lookup"><span data-stu-id="64eb7-138">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
- [<span data-ttu-id="64eb7-139">\<Мессажелоггинг ></span><span class="sxs-lookup"><span data-stu-id="64eb7-139">\<messageLogging></span></span>](messagelogging.md)
