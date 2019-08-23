---
title: <routing> из <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 73a610056f94efe144705968eaf97c8314c1ae0d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934200"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="3f57e-102">\<> маршрутизации > \<ServiceBehavior</span><span class="sxs-lookup"><span data-stu-id="3f57e-102">\<routing> of \<serviceBehavior></span></span>
<span data-ttu-id="3f57e-103">Обеспечивает доступ к службе маршрутизации во время выполнения, чтобы вносить динамические изменения в конфигурацию маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="3f57e-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
 <span data-ttu-id="3f57e-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3f57e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3f57e-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="3f57e-105">\<behaviors></span></span>  
<span data-ttu-id="3f57e-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3f57e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="3f57e-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="3f57e-107">\<behavior></span></span>  
<span data-ttu-id="3f57e-108">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="3f57e-108">\<routing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f57e-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f57e-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f57e-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3f57e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3f57e-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3f57e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f57e-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3f57e-112">Attributes</span></span>  
  
|<span data-ttu-id="3f57e-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3f57e-113">Attribute</span></span>|<span data-ttu-id="3f57e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3f57e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3f57e-115">filterTable</span><span class="sxs-lookup"><span data-stu-id="3f57e-115">filterTable</span></span>|<span data-ttu-id="3f57e-116">Строка, в которой указано имя таблицы маршрутизации, содержащей фильтры, вычисляемые службой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="3f57e-116">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="3f57e-117">Это значение должно соответствовать `name` атрибуту [ \<элемента филтертабле >](filtertable.md) в [ \<разделе филтертаблес >](filtertables.md) .</span><span class="sxs-lookup"><span data-stu-id="3f57e-117">This value must match the `name` attribute of a [\<filterTable>](filtertable.md) element in the [\<filterTables>](filtertables.md) section.</span></span>|  
|<span data-ttu-id="3f57e-118">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="3f57e-118">routeOnHeaderOnly</span></span>|<span data-ttu-id="3f57e-119">Логическое значение, определяющее, какие части сообщения будут изучены фильтром: только заголовок или заголовок и текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="3f57e-119">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="3f57e-120">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="3f57e-120">The default is `true`.</span></span>|  
|<span data-ttu-id="3f57e-121">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="3f57e-121">soapProcessingEnabled</span></span>|<span data-ttu-id="3f57e-122">Логическое значение, указывающее, будет ли выполняться обработка SOAP.</span><span class="sxs-lookup"><span data-stu-id="3f57e-122">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f57e-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3f57e-123">Child Elements</span></span>  
 <span data-ttu-id="3f57e-124">Нет.</span><span class="sxs-lookup"><span data-stu-id="3f57e-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f57e-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3f57e-125">Parent Elements</span></span>  
  
|<span data-ttu-id="3f57e-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="3f57e-126">Element</span></span>|<span data-ttu-id="3f57e-127">Описание</span><span class="sxs-lookup"><span data-stu-id="3f57e-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f57e-128">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="3f57e-128">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3f57e-129">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="3f57e-129">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f57e-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="3f57e-130">Remarks</span></span>  
 <span data-ttu-id="3f57e-131">Если добавить к конфигурации поведения службы, этот элемент конфигурации включает маршрутизацию для службы.</span><span class="sxs-lookup"><span data-stu-id="3f57e-131">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="3f57e-132">В этом элементе можно указать фактическую таблицу маршрутизации, которая будет использоваться службой.</span><span class="sxs-lookup"><span data-stu-id="3f57e-132">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="3f57e-133">Используя этот раздел конфигурации, можно на лету изменять параметры маршрутизации при изменении шаблона развертывания.</span><span class="sxs-lookup"><span data-stu-id="3f57e-133">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="3f57e-134">Во время выполнения можно зарегистрировать собственное расширение маршрутизации с новыми параметрами. В этом случае служба маршрутизации будет использовать обновленную конфигурацию для новых сеансов и сообщений (для уже запущенных на данных момент сообщений и сеансов будут применяться правила, действовавшие в момент их запуска).</span><span class="sxs-lookup"><span data-stu-id="3f57e-134">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="3f57e-135">Благодаря этому обеспечивается безопасная для сеансов и не требующая перезапуска повторная настройка службы маршрутизации во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="3f57e-135">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
