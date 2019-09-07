---
title: <routing> из <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 0998f4fc61de7099879ba6e122eed1e64588baec
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397734"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="b089b-102">\<> маршрутизации > \<ServiceBehavior</span><span class="sxs-lookup"><span data-stu-id="b089b-102">\<routing> of \<serviceBehavior></span></span>
<span data-ttu-id="b089b-103">Обеспечивает доступ к службе маршрутизации во время выполнения, чтобы вносить динамические изменения в конфигурацию маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="b089b-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
<span data-ttu-id="b089b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b089b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b089b-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b089b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b089b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b089b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="b089b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b089b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="b089b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b089b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="b089b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> маршрутизации**</span><span class="sxs-lookup"><span data-stu-id="b089b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b089b-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b089b-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <routing filterTable="String"
               routeOnHeadersOnly="Boolean"
               SoapProcessingEnabled="Boolean" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b089b-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b089b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b089b-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b089b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b089b-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b089b-113">Attributes</span></span>  
  
|<span data-ttu-id="b089b-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b089b-114">Attribute</span></span>|<span data-ttu-id="b089b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b089b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b089b-116">filterTable</span><span class="sxs-lookup"><span data-stu-id="b089b-116">filterTable</span></span>|<span data-ttu-id="b089b-117">Строка, в которой указано имя таблицы маршрутизации, содержащей фильтры, вычисляемые службой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="b089b-117">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="b089b-118">Это значение должно соответствовать `name` атрибуту [ \<элемента филтертабле >](filtertable.md) в [ \<разделе филтертаблес >](filtertables.md) .</span><span class="sxs-lookup"><span data-stu-id="b089b-118">This value must match the `name` attribute of a [\<filterTable>](filtertable.md) element in the [\<filterTables>](filtertables.md) section.</span></span>|  
|<span data-ttu-id="b089b-119">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="b089b-119">routeOnHeaderOnly</span></span>|<span data-ttu-id="b089b-120">Логическое значение, определяющее, какие части сообщения будут изучены фильтром: только заголовок или заголовок и текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="b089b-120">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="b089b-121">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="b089b-121">The default is `true`.</span></span>|  
|<span data-ttu-id="b089b-122">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="b089b-122">soapProcessingEnabled</span></span>|<span data-ttu-id="b089b-123">Логическое значение, указывающее, будет ли выполняться обработка SOAP.</span><span class="sxs-lookup"><span data-stu-id="b089b-123">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b089b-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b089b-124">Child Elements</span></span>  
 <span data-ttu-id="b089b-125">Нет.</span><span class="sxs-lookup"><span data-stu-id="b089b-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b089b-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b089b-126">Parent Elements</span></span>  
  
|<span data-ttu-id="b089b-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="b089b-127">Element</span></span>|<span data-ttu-id="b089b-128">Описание</span><span class="sxs-lookup"><span data-stu-id="b089b-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b089b-129">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="b089b-129">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="b089b-130">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="b089b-130">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b089b-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="b089b-131">Remarks</span></span>  
 <span data-ttu-id="b089b-132">Если добавить к конфигурации поведения службы, этот элемент конфигурации включает маршрутизацию для службы.</span><span class="sxs-lookup"><span data-stu-id="b089b-132">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="b089b-133">В этом элементе можно указать фактическую таблицу маршрутизации, которая будет использоваться службой.</span><span class="sxs-lookup"><span data-stu-id="b089b-133">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="b089b-134">Используя этот раздел конфигурации, можно на лету изменять параметры маршрутизации при изменении шаблона развертывания.</span><span class="sxs-lookup"><span data-stu-id="b089b-134">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="b089b-135">Во время выполнения можно зарегистрировать собственное расширение маршрутизации с новыми параметрами. В этом случае служба маршрутизации будет использовать обновленную конфигурацию для новых сеансов и сообщений (для уже запущенных на данных момент сообщений и сеансов будут применяться правила, действовавшие в момент их запуска).</span><span class="sxs-lookup"><span data-stu-id="b089b-135">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="b089b-136">Благодаря этому обеспечивается безопасная для сеансов и не требующая перезапуска повторная настройка службы маршрутизации во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b089b-136">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
