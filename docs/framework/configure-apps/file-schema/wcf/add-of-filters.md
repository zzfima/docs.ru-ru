---
title: <add> из <filters>
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: 399fc4e22a9253469a5494af61dac862e33814a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128704"
---
# <a name="add-of-filters"></a><span data-ttu-id="a7b35-102">\<Добавить > из \<фильтры ></span><span class="sxs-lookup"><span data-stu-id="a7b35-102">\<add> of \<filters></span></span>
<span data-ttu-id="a7b35-103">Фильтр XPath, задающий тип сообщений для записи в журнал.</span><span class="sxs-lookup"><span data-stu-id="a7b35-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
 <span data-ttu-id="a7b35-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a7b35-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a7b35-105">\<диагностические ></span><span class="sxs-lookup"><span data-stu-id="a7b35-105">\<diagnostic></span></span>  
<span data-ttu-id="a7b35-106">\<messageLogging ></span><span class="sxs-lookup"><span data-stu-id="a7b35-106">\<messageLogging></span></span>  
<span data-ttu-id="a7b35-107">\<Фильтры ></span><span class="sxs-lookup"><span data-stu-id="a7b35-107">\<filters></span></span>  
<span data-ttu-id="a7b35-108">\<add></span><span class="sxs-lookup"><span data-stu-id="a7b35-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7b35-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7b35-109">Syntax</span></span>  
  
```xml  
<filters>
  <add filter="String" />
</filters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7b35-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a7b35-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a7b35-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a7b35-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7b35-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a7b35-112">Attributes</span></span>  
  
|<span data-ttu-id="a7b35-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a7b35-113">Attribute</span></span>|<span data-ttu-id="a7b35-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a7b35-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a7b35-115">фильтр</span><span class="sxs-lookup"><span data-stu-id="a7b35-115">filter</span></span>|<span data-ttu-id="a7b35-116">Строка, задающая запрос к документу XML, определенный в виде выражения XPath 1.0.</span><span class="sxs-lookup"><span data-stu-id="a7b35-116">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="a7b35-117">Дополнительные сведения см. в разделе <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="a7b35-117">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7b35-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a7b35-118">Child Elements</span></span>  
 <span data-ttu-id="a7b35-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a7b35-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a7b35-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a7b35-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a7b35-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="a7b35-121">Element</span></span>|<span data-ttu-id="a7b35-122">Описание</span><span class="sxs-lookup"><span data-stu-id="a7b35-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7b35-123">\<Фильтры></span><span class="sxs-lookup"><span data-stu-id="a7b35-123">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters.md)|<span data-ttu-id="a7b35-124">Содержит коллекцию фильтров XPath, используемых для контроля типов регистрируемых сообщений.</span><span class="sxs-lookup"><span data-stu-id="a7b35-124">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7b35-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="a7b35-125">Remarks</span></span>  
 <span data-ttu-id="a7b35-126">Фильтры применяются только на транспортном уровне, когда параметр `logMessagesAtTransportLevel` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="a7b35-126">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="a7b35-127">Фильтры не влияют на ведение журнала сообщений уровня службы и неправильно сформированных сообщений.</span><span class="sxs-lookup"><span data-stu-id="a7b35-127">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="a7b35-128">Для добавления нового фильтра в коллекцию используется ключевое слово `add`.</span><span class="sxs-lookup"><span data-stu-id="a7b35-128">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="a7b35-129">Если в файле конфигурации определены один или несколько фильтров, в журнал записываются только сообщения, соответствующие хотя бы одному из фильтров.</span><span class="sxs-lookup"><span data-stu-id="a7b35-129">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="a7b35-130">Если фильтры не заданы, в журнал записываются все сообщения.</span><span class="sxs-lookup"><span data-stu-id="a7b35-130">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="a7b35-131">Фильтры поддерживают полный синтаксис XPath и применяются в том порядке, в котором они записаны в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a7b35-131">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="a7b35-132">Синтаксически неверные фильтры вызывают исключения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a7b35-132">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="a7b35-133">В следующем примере показано, как настроить фильтр для записи только сообщений с разделом заголовка SOAP.</span><span class="sxs-lookup"><span data-stu-id="a7b35-133">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7b35-134">Пример</span><span class="sxs-lookup"><span data-stu-id="a7b35-134">Example</span></span>  
 <span data-ttu-id="a7b35-135">В следующем примере показано, как настроить фильтр для записи только сообщений с разделом заголовка SOAP.</span><span class="sxs-lookup"><span data-stu-id="a7b35-135">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a7b35-136">См. также</span><span class="sxs-lookup"><span data-stu-id="a7b35-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="a7b35-137">Настройка ведения журналов сообщений</span><span class="sxs-lookup"><span data-stu-id="a7b35-137">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)
- [<span data-ttu-id="a7b35-138">\<messageLogging ></span><span class="sxs-lookup"><span data-stu-id="a7b35-138">\<messageLogging></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)
