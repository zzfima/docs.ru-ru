---
title: Выбор фильтра
ms.date: 03/30/2017
ms.assetid: 67ab5af9-b9d9-4300-b3b1-41abb5a1fd10
ms.openlocfilehash: 91b3802217a920ef3eeeccb5c4f85c66afee2430
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="choosing-a-filter"></a><span data-ttu-id="1724b-102">Выбор фильтра</span><span class="sxs-lookup"><span data-stu-id="1724b-102">Choosing a Filter</span></span>
<span data-ttu-id="1724b-103">При настройке службы маршрутизации важно выбрать правильные фильтры сообщений и настроить их таким образом, чтобы полученное сообщение всегда определялось одним из них.</span><span class="sxs-lookup"><span data-stu-id="1724b-103">When configuring the Routing Service, it is important to select correct message filters and configure them to allow you to make exact matches against the messages you receive.</span></span> <span data-ttu-id="1724b-104">Если выбранные фильтры допускают избыточные совпадения или неверно настроены, то сообщения будут маршрутизироваться неправильно.</span><span class="sxs-lookup"><span data-stu-id="1724b-104">If the filters you select are overly broad in their matches or are incorrectly configured, messages are routed incorrectly.</span></span> <span data-ttu-id="1724b-105">Если фильтры слишком строги, то это может привести к тому, что для некоторых сообщений не окажется ни одного допустимого маршрута.</span><span class="sxs-lookup"><span data-stu-id="1724b-105">If the filters are too restrictive, you may not have any valid routes available for some of your messages.</span></span>  
  
## <a name="filter-types"></a><span data-ttu-id="1724b-106">Типы фильтров</span><span class="sxs-lookup"><span data-stu-id="1724b-106">Filter Types</span></span>  
 <span data-ttu-id="1724b-107">При выборе фильтров, используемых службой маршрутизации, важно понимать, каким образом работает каждый из них и какие сведения имеются во входящих сообщениях.</span><span class="sxs-lookup"><span data-stu-id="1724b-107">When selecting the filters that are used by the Routing Service, it is important that you understand how each filter works as well as what information is available as part of the incoming messages.</span></span> <span data-ttu-id="1724b-108">Например, если все сообщения получаются одной и той же конечной точкой, то фильтры Address и EndpointName не рекомендуется использовать вместе, так как все сообщения будут определены этими фильтрами.</span><span class="sxs-lookup"><span data-stu-id="1724b-108">For instance, if all messages are received over the same endpoint, the Address and EndpointName filters are not useful because all messages match these filters.</span></span>  
  
### <a name="action"></a><span data-ttu-id="1724b-109">Действие</span><span class="sxs-lookup"><span data-stu-id="1724b-109">Action</span></span>  
 <span data-ttu-id="1724b-110">Фильтр Action проверяет свойство <xref:System.ServiceModel.Channels.MessageHeaders.Action%2A>.</span><span class="sxs-lookup"><span data-stu-id="1724b-110">The Action filter inspects the <xref:System.ServiceModel.Channels.MessageHeaders.Action%2A> property.</span></span> <span data-ttu-id="1724b-111">Если содержимое заголовка Action в сообщении соответствует значению данных фильтра, которое указано в конфигурации фильтра, то этот фильтр возвращает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="1724b-111">If the contents of the Action header in the message match the filter data value specified in the filter configuration, then this filter returns `true`.</span></span> <span data-ttu-id="1724b-112">В следующем примере определяется `FilterElement` , использует действие фильтра для поиска сообщений с заголовком action, который содержит значение «http://namespace/contract/operation/».</span><span class="sxs-lookup"><span data-stu-id="1724b-112">The following example defines a `FilterElement` that uses the Action filter to match messages with an action header that contains a value of "http://namespace/contract/operation/".</span></span>  
  
```xml  
<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation/" />  
```  
  
```csharp  
ActionMessageFilter action1 = new ActionMessageFilter(new string[] { "http://namespace/contract/operation" });  
```  
  
 <span data-ttu-id="1724b-113">Этот фильтр следует использовать при маршрутизации сообщений, которые содержат заголовок Action.</span><span class="sxs-lookup"><span data-stu-id="1724b-113">This filter should be used when routing messages that contain a unique Action header.</span></span>  
  
### <a name="endpointaddress"></a><span data-ttu-id="1724b-114">EndpointAddress</span><span class="sxs-lookup"><span data-stu-id="1724b-114">EndpointAddress</span></span>  
 <span data-ttu-id="1724b-115">Фильтр EndpointAddress проверяет адрес конечной точки, которой было получено сообщение.</span><span class="sxs-lookup"><span data-stu-id="1724b-115">The EndpointAddress filter inspects the EndpointAddress that the message was received on.</span></span> <span data-ttu-id="1724b-116">Если адрес, на который получено сообщение, совпадает с адресом фильтра, указанным в его конфигурации, то этот фильтр возвращает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="1724b-116">If the address that the message arrives at exactly matches the filter address specified in the filter configuration, then this filter returns `true`.</span></span> <span data-ttu-id="1724b-117">В следующем примере определяется `FilterElement` , использует фильтр Address для поиска всех сообщений, адресованных «http://\<hostname > / vdir/s.svc/b».</span><span class="sxs-lookup"><span data-stu-id="1724b-117">The following example defines a `FilterElement` that uses the Address filter to match any messages addressed to "http://\<hostname>/vdir/s.svc/b".</span></span>  
  
```xml  
<filter name="address1" filterType="EndpointAddress" filterData="http://host/vdir/s.svc/b" />  
```  
  
```csharp  
EndpointAddressMessageFilter address1 = new EndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);  
```  
  
> [!NOTE]
>  <span data-ttu-id="1724b-118">Важно обратить внимание, что часть имени узла в адресе может отличаться в зависимости от того, использует ли клиент полное доменное имя, имя NetBIOS, IP-адрес или другое имя.</span><span class="sxs-lookup"><span data-stu-id="1724b-118">It is important to note that the host name portion of an address can differ based on whether the client uses the fully qualified domain name, NetBIOS name, IP address, or other name.</span></span> <span data-ttu-id="1724b-119">Поскольку разные значения могут указывать на один и тот же узел, по умолчанию при выполнении сопоставлений это сравнение не использует часть адреса, которая обозначает имя узла.</span><span class="sxs-lookup"><span data-stu-id="1724b-119">Because differing values can refer to the same host, the default behavior for this comparison is to not use the host name portion of the address when performing matches.</span></span>  
>   
>  <span data-ttu-id="1724b-120">Это можно изменить программным способом при настройке службы маршрутизации, разрешив сравнение для определения имени узла.</span><span class="sxs-lookup"><span data-stu-id="1724b-120">This behavior can be modified to allow the comparison to evaluate the host name when configuring the Routing Service programmatically.</span></span>  
  
 <span data-ttu-id="1724b-121">Этот фильтр следует использовать в том случае, когда входящие сообщения адресованы по уникальному адресу.</span><span class="sxs-lookup"><span data-stu-id="1724b-121">This filter should be used when the incoming messages are addressed to a unique address.</span></span>  
  
### <a name="endpointaddressprefix"></a><span data-ttu-id="1724b-122">EndpointAddressPrefix</span><span class="sxs-lookup"><span data-stu-id="1724b-122">EndpointAddressPrefix</span></span>  
 <span data-ttu-id="1724b-123">Фильтр EndpointAddressPrefix аналогичен фильтру EndpointAddress.</span><span class="sxs-lookup"><span data-stu-id="1724b-123">The EndpointAddressPrefix filter is similar to the EndpointAddress filter.</span></span> <span data-ttu-id="1724b-124">Он также проверяет адрес конечной точки, на который было получено сообщение.</span><span class="sxs-lookup"><span data-stu-id="1724b-124">The EndpointAddressPrefix filter inspects the EndpointAddress that the message was received on.</span></span> <span data-ttu-id="1724b-125">Однако EndpointAddressPrefix ищет совпадение начала адреса с шаблоном, заданным в конфигурации фильтра.</span><span class="sxs-lookup"><span data-stu-id="1724b-125">However the EndpointAddressPrefix filter acts as a wildcard by matching addresses that begin with the value specified in the filter configuration.</span></span> <span data-ttu-id="1724b-126">В следующем примере определяется `FilterElement` , использует фильтр EndpointAddressPrefix для поиска всех сообщений, адресованных «http://\<hostname > / vdir \*».</span><span class="sxs-lookup"><span data-stu-id="1724b-126">The following example defines a `FilterElement` that uses the EndpointAddressPrefix filter to match any messages addressed to "http://\<hostname>/vdir\*".</span></span>  
  
```xml  
<filter name="prefix1" filterType="EndpointAddressPrefix" filterData="http://host/vdir" />  
```  
  
```csharp  
PrefixEndpointAddressMessageFilter prefix1 = new PrefixEndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);  
```  
  
> [!NOTE]
>  <span data-ttu-id="1724b-127">Важно обратить внимание, что часть имени узла в адресе может отличаться в зависимости от того, использует ли клиент полное доменное имя, имя NetBIOS, IP-адрес или другое имя.</span><span class="sxs-lookup"><span data-stu-id="1724b-127">It is important to note that the host name portion of an address can differ based on whether the client uses the fully qualified domain name, NetBIOS name, IP address, or other name.</span></span> <span data-ttu-id="1724b-128">Поскольку разные значения могут указывать на один и тот же узел, по умолчанию при выполнении сопоставлений это сравнение не использует часть адреса, которая обозначает имя узла.</span><span class="sxs-lookup"><span data-stu-id="1724b-128">Because differing values can refer to the same host, the default behavior for this comparison is to not use the host name portion of the address when performing matches.</span></span>  
  
 <span data-ttu-id="1724b-129">Этот фильтр необходимо использовать при маршрутизации входящих сообщений, которые совместно используют общий префикс адреса.</span><span class="sxs-lookup"><span data-stu-id="1724b-129">This filter should be used when routing incoming messages that share a common address prefix.</span></span>  
  
### <a name="and"></a><span data-ttu-id="1724b-130">AND</span><span class="sxs-lookup"><span data-stu-id="1724b-130">AND</span></span>  
 <span data-ttu-id="1724b-131">Фильтр `AND` не выполняет непосредственную фильтрацию по значению в сообщении. Он позволяет объединять два других фильтра, создав условие логического умножения, при котором оба фильтра должны соответствовать сообщению, чтобы результат оценки фильтра принял значение `true`.</span><span class="sxs-lookup"><span data-stu-id="1724b-131">The AND filter does not directly filter on a value within a message, but allows you to combine two other filters to create an `AND` condition where both filters must match the message before the AND filter evaluates to `true`.</span></span> <span data-ttu-id="1724b-132">Это позволяет создавать сложные фильтры, которые находят совпадение только тогда, когда совпадения имеются по всем вложенным фильтрам.</span><span class="sxs-lookup"><span data-stu-id="1724b-132">This allows you to create complex filters that only match if all the sub-filters match.</span></span> <span data-ttu-id="1724b-133">В следующем примере определен фильтр по адресу и фильтр по действию, затем определен фильтр AND, который проверяет сообщение по фильтру адреса и по фильтру действия.</span><span class="sxs-lookup"><span data-stu-id="1724b-133">The following example defines an address filter and an action filter, and then defines an AND filter that evaluates a message against both the address and action filters.</span></span> <span data-ttu-id="1724b-134">Если фильтры по адресу и по действию нашли совпадение, то фильтр AND возвращает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="1724b-134">If both the address and the action filters match, then the AND filter returns `true`.</span></span>  
  
```xml  
<filter name="address1" filterType="AddressPrefix" filterData="http://host/vdir"/>  
<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation/"/>  
<filter name="and1" filterType="And" filter1="address1" filter2="action1" />  
```  
  
```csharp  
EndpointAddressMessageFilter address1 = new EndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);  
ActionMessageFilter action1 = new ActionMessageFilter(new string[] { "http://namespace/contract/operation" });  
StrictAndMessageFilter and1=new StrictAndMessageFilter(address1, action1);  
```  
  
 <span data-ttu-id="1724b-135">Этот фильтр должен использоваться в тех случаях, когда необходимо логически объединить несколько фильтров.</span><span class="sxs-lookup"><span data-stu-id="1724b-135">This filter should be used when you must combine the logic from multiple filters to determine when a match should be made.</span></span> <span data-ttu-id="1724b-136">Например, если существует несколько целевых объектов, которые должны получать только определенные сочетания действий и сообщений по определенным адресам, то можно объединить фильтры Action и Address с помощью фильтра AND.</span><span class="sxs-lookup"><span data-stu-id="1724b-136">For example, if you have multiple destinations that must receive only certain combinations of actions and messages to particular addresses, you can use an AND filter to combine the necessary Action and Address filters.</span></span>  
  
### <a name="custom"></a><span data-ttu-id="1724b-137">Другой</span><span class="sxs-lookup"><span data-stu-id="1724b-137">Custom</span></span>  
 <span data-ttu-id="1724b-138">При выборе типа фильтра Custom необходимо указать значение customType, содержащее тип сборки, содержащей **MessageFilter** реализации для использования этого фильтра.</span><span class="sxs-lookup"><span data-stu-id="1724b-138">When selecting the Custom filter type, you must provide a customType value that contains the type of the assembly that contains the **MessageFilter** implementation to be used for this filter.</span></span> <span data-ttu-id="1724b-139">Кроме того, filterData должно содержать все значения, которые пользовательскому фильтру могут потребоваться для проверки сообщений.</span><span class="sxs-lookup"><span data-stu-id="1724b-139">Additionally, filterData must contain any values that the custom filter may require in its evaluation of messages.</span></span> <span data-ttu-id="1724b-140">В следующем примере определяется `FilterElement`, который использует реализацию класса MessageFilter - `CustomAssembly.MyCustomMsgFilter`.</span><span class="sxs-lookup"><span data-stu-id="1724b-140">The following example defines a `FilterElement` that uses the `CustomAssembly.MyCustomMsgFilter` MessageFilter implementation.</span></span>  
  
```xml  
<filter name="custom1" filterType="Custom" customType="CustomAssembly.MyCustomMsgFilter, CustomAssembly" filterData="Custom Data" />  
```  
  
```csharp  
MyCustomMsgFilter custom1=new MyCustomMsgFilter("Custom Data");  
```  
  
 <span data-ttu-id="1724b-141">Если необходимо выполнить пользовательскую логику сопоставления сообщение, не связанная с фильтрами, имеющимися в [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], необходимо создать пользовательский фильтр, который является реализацией **MessageFilter** класса.</span><span class="sxs-lookup"><span data-stu-id="1724b-141">If you need to perform custom matching logic against a message that is not covered by the filters provided with [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], you must create a custom filter that is an implementation of the **MessageFilter** class.</span></span> <span data-ttu-id="1724b-142">Например, можно создать пользовательский фильтр, который сравнивает поле во входящем сообщении со списком известных значений, заданных в конфигурации фильтра. Либо можно создать фильтр, который выполняет хэширование определенного элемента сообщения, а затем проверяет это значение, чтобы определить, какое значение должен вернуть фильтр - `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="1724b-142">For example, you might create a custom filter that compares a field in the incoming message against a list of known values given to the filter as configuration, or that hashes a particular message element and then examines that value to determine whether the filter should return `true` or `false`.</span></span>  
  
### <a name="endpointname"></a><span data-ttu-id="1724b-143">EndpointName</span><span class="sxs-lookup"><span data-stu-id="1724b-143">EndpointName</span></span>  
 <span data-ttu-id="1724b-144">Фильтр EndpointName проверяет имя конечной точки, которая получила сообщение.</span><span class="sxs-lookup"><span data-stu-id="1724b-144">The EndpointName filter inspects the name of the endpoint that received the message.</span></span> <span data-ttu-id="1724b-145">В следующем примере определяется `FilterElement` , использует фильтр EndpointName для маршрутизации сообщений, полученных в «svcendpoint».</span><span class="sxs-lookup"><span data-stu-id="1724b-145">The following example defines a `FilterElement` that uses the EndpointName filter to route messages received on the "SvcEndpoint".</span></span>  
  
```xml  
<filter name="name1" filterType="Endpoint" filterData="SvcEndpoint" />  
```  
  
```csharp  
EndpointNameMessageFilter name1 = new EndpointNameMessageFilter("SvcEndpoint");  
```  
  
 <span data-ttu-id="1724b-146">Этот фильтр рекомендуется использовать в тех случаях, когда служба маршрутизации обеспечивает доступ к нескольким именованным конечным точкам служб.</span><span class="sxs-lookup"><span data-stu-id="1724b-146">This filter is useful when the Routing Service exposes more than one named service endpoint.</span></span> <span data-ttu-id="1724b-147">Например, можно реализовать две конечные точки, используемые службой маршрутизации для получения сообщений. Одна из них предназначена для важных клиентов, которым требуется обработка сообщений в режиме реального времени, а вторая будет обрабатывать сообщения, время обработки которых не критично.</span><span class="sxs-lookup"><span data-stu-id="1724b-147">For example, you might expose two endpoints that the Routing Service uses to receive messages; one is used by priority customers who require real-time processing of their messages, while the other endpoint receives messages that are not time sensitive.</span></span>  
  
 <span data-ttu-id="1724b-148">Можно использовать сопоставление по полному адресу для определения конечной точки, которая получила сообщение, однако использование вместо этого конкретного имени конечной точки является более удобным способом, который обычно менее подвержен ошибкам, особенно при настройке службы маршрутизации через файл конфигурации (где имена конечных точек являются обязательными атрибутами).</span><span class="sxs-lookup"><span data-stu-id="1724b-148">While you can often use full address matching to determine which endpoint a message was received on, using the defined endpoint name instead is a convenient shortcut that is often less error prone, especially when configuring a Routing Service using a configuration file (where endpoint names are a required attribute).</span></span>  
  
### <a name="matchall"></a><span data-ttu-id="1724b-149">MatchAll</span><span class="sxs-lookup"><span data-stu-id="1724b-149">MatchAll</span></span>  
 <span data-ttu-id="1724b-150">Фильтр MatchAll выполняет сопоставление всех полученных сообщений.</span><span class="sxs-lookup"><span data-stu-id="1724b-150">The MatchAll filter matches any received message.</span></span> <span data-ttu-id="1724b-151">Этот фильтр рекомендуется к использованию в том случае, если необходима маршрутизация абсолютно всех полученных сообщений определенной конечной точке, например службе ведения журнала, которая сохраняет копии всех полученных сообщений.</span><span class="sxs-lookup"><span data-stu-id="1724b-151">It is useful if you must always route all received messages to a specific endpoint, such as a logging service that stores a copy of all received messages.</span></span> <span data-ttu-id="1724b-152">В следующем примере определяется `FilterElement`, который использует фильтр MatchAll.</span><span class="sxs-lookup"><span data-stu-id="1724b-152">The following example defines a `FilterElement` that uses the MatchAll filter.</span></span>  
  
```xml  
<filter name="matchAll1" filterType="MatchAll" />  
```  
  
```csharp  
MatchAllMessageFilter matchAll1 = new MatchAllMessageFilter();  
```  
  
### <a name="xpath"></a><span data-ttu-id="1724b-153">XPath</span><span class="sxs-lookup"><span data-stu-id="1724b-153">XPath</span></span>  
 <span data-ttu-id="1724b-154">Фильтр XPath позволяет указать запрос XPath, который используется для проверки определенного элемента в сообщении.</span><span class="sxs-lookup"><span data-stu-id="1724b-154">The XPath filter allows you to specify an XPath query that is used to inspect a specific element within the message.</span></span> <span data-ttu-id="1724b-155">Фильтрация XPath является эффективным способом фильтрации, который позволяет напрямую проверять все адресуемые XML-записи в сообщении. Однако для использования этого фильтра необходимо иметь определенные сведения о структуре получаемых сообщений.</span><span class="sxs-lookup"><span data-stu-id="1724b-155">XPath filtering is a powerful filtering option that allows you to directly inspect any XML addressable entry within the message; however it requires that you have specific knowledge of the structure of the messages that you are receiving.</span></span> <span data-ttu-id="1724b-156">В следующем примере определяется `FilterElement` , использует фильтр XPath для проверки сообщений на наличие элемента с именем «element» в пространстве имен, на который указывает префикс пространства имен «ns».</span><span class="sxs-lookup"><span data-stu-id="1724b-156">The following example defines a `FilterElement` that uses the XPath filter to inspect the message for an element named "element" within the namespace referenced by the "ns" namespace prefix.</span></span>  
  
```xml  
<filter name="xpath1" filterType="XPath" filterData="//ns:element" />  
```  
  
```csharp  
XPathMessageFilter xpath1=new XPathMessageFilter("//ns:element");  
```  
  
 <span data-ttu-id="1724b-157">Этим фильтром рекомендуется пользоваться в тех случаях, когда точно известно, что получаемое сообщение содержит определенное значение.</span><span class="sxs-lookup"><span data-stu-id="1724b-157">This filter is useful if you know that the messages you are receiving contain a specific value.</span></span> <span data-ttu-id="1724b-158">Например, если размещаются две версии одной службы и известно, что сообщение, которое адресовано более новой версии службы, содержит уникальное значение в пользовательском заголовке, можно создать фильтр, который использует XPath для перехода к этому заголовку и выполняет сравнение значения, которое находится в заголовке, со значением, которое указано в конфигурации фильтра, для определения его соответствия фильтру.</span><span class="sxs-lookup"><span data-stu-id="1724b-158">For example, if you are hosting two versions of the same service and you know that messages addressed to the newer version of the service contain a unique value in a custom header, you can create a filter that uses XPath to navigate to this header and compares the value present in the header to another given in the filter configuration to determine if the filter matches.</span></span>  
  
 <span data-ttu-id="1724b-159">Поскольку запросы XPath часто содержат уникальные пространства имен, которые часто представлены очень длинными или сложными строковыми значениями, фильтр XPath позволяет использовать таблицу пространств имен, в которой для пространств имен можно определить уникальные префиксы.</span><span class="sxs-lookup"><span data-stu-id="1724b-159">Because XPath queries often contain unique namespaces, which are often lengthy or complex string values, the XPath filter allows you to use the namespace table to define unique prefixes for your namespaces.</span></span> <span data-ttu-id="1724b-160">Дополнительные сведения о таблице пространств имен см. в разделе [фильтры сообщений](../../../../docs/framework/wcf/feature-details/message-filters.md).</span><span class="sxs-lookup"><span data-stu-id="1724b-160">For more information about the namespace table, see [Message Filters](../../../../docs/framework/wcf/feature-details/message-filters.md).</span></span>  
  
 <span data-ttu-id="1724b-161">Дополнительные сведения о проектировании запросов XPath см. в разделе [синтаксис XPath](http://go.microsoft.com/fwlink/?LinkId=164592).</span><span class="sxs-lookup"><span data-stu-id="1724b-161">For more information about designing XPath queries, see [XPath Syntax](http://go.microsoft.com/fwlink/?LinkId=164592).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1724b-162">См. также</span><span class="sxs-lookup"><span data-stu-id="1724b-162">See Also</span></span>  
 [<span data-ttu-id="1724b-163">Фильтры сообщений</span><span class="sxs-lookup"><span data-stu-id="1724b-163">Message Filters</span></span>](../../../../docs/framework/wcf/feature-details/message-filters.md)  
 [<span data-ttu-id="1724b-164">Практическое руководство. Использование фильтров</span><span class="sxs-lookup"><span data-stu-id="1724b-164">How To: Use Filters</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-filters.md)
