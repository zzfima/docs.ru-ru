---
title: '&lt;маршрутизация&gt; для &lt;serviceBehavior&gt;'
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 5fb7febe365f73acf09ba74b07215fe9cc659efb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750756"
---
# <a name="ltroutinggt-of-ltservicebehaviorgt"></a><span data-ttu-id="12d2f-102">&lt;маршрутизация&gt; для &lt;serviceBehavior&gt;</span><span class="sxs-lookup"><span data-stu-id="12d2f-102">&lt;routing&gt; of &lt;serviceBehavior&gt;</span></span>
<span data-ttu-id="12d2f-103">Обеспечивает доступ к службе маршрутизации во время выполнения, чтобы вносить динамические изменения в конфигурацию маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="12d2f-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
 <span data-ttu-id="12d2f-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="12d2f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="12d2f-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="12d2f-105">\<behaviors></span></span>  
<span data-ttu-id="12d2f-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="12d2f-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="12d2f-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="12d2f-107">\<behavior></span></span>  
<span data-ttu-id="12d2f-108">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="12d2f-108">\<routing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12d2f-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12d2f-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12d2f-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="12d2f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="12d2f-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="12d2f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12d2f-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="12d2f-112">Attributes</span></span>  
  
|<span data-ttu-id="12d2f-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="12d2f-113">Attribute</span></span>|<span data-ttu-id="12d2f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="12d2f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="12d2f-115">filterTable</span><span class="sxs-lookup"><span data-stu-id="12d2f-115">filterTable</span></span>|<span data-ttu-id="12d2f-116">Строка, в которой указано имя таблицы маршрутизации, содержащей фильтры, вычисляемые службой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="12d2f-116">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="12d2f-117">Это значение должно соответствовать `name` атрибут [ \<filterTable >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) элемент в [ \<filterTables >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="12d2f-117">This value must match the `name` attribute of a [\<filterTable>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) element in the [\<filterTables>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) section.</span></span>|  
|<span data-ttu-id="12d2f-118">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="12d2f-118">routeOnHeaderOnly</span></span>|<span data-ttu-id="12d2f-119">Логическое значение, определяющее, какие части сообщения будут изучены фильтром: только заголовок или заголовок и текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="12d2f-119">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="12d2f-120">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="12d2f-120">The default is `true`.</span></span>|  
|<span data-ttu-id="12d2f-121">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="12d2f-121">soapProcessingEnabled</span></span>|<span data-ttu-id="12d2f-122">Логическое значение, указывающее, будет ли выполняться обработка SOAP.</span><span class="sxs-lookup"><span data-stu-id="12d2f-122">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="12d2f-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="12d2f-123">Child Elements</span></span>  
 <span data-ttu-id="12d2f-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="12d2f-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="12d2f-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="12d2f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="12d2f-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="12d2f-126">Element</span></span>|<span data-ttu-id="12d2f-127">Описание</span><span class="sxs-lookup"><span data-stu-id="12d2f-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12d2f-128">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="12d2f-128">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="12d2f-129">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="12d2f-129">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12d2f-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="12d2f-130">Remarks</span></span>  
 <span data-ttu-id="12d2f-131">Если добавить к конфигурации поведения службы, этот элемент конфигурации включает маршрутизацию для службы.</span><span class="sxs-lookup"><span data-stu-id="12d2f-131">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="12d2f-132">В этом элементе можно указать фактическую таблицу маршрутизации, которая будет использоваться службой.</span><span class="sxs-lookup"><span data-stu-id="12d2f-132">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="12d2f-133">Используя этот раздел конфигурации, можно на лету изменять параметры маршрутизации при изменении шаблона развертывания.</span><span class="sxs-lookup"><span data-stu-id="12d2f-133">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="12d2f-134">Во время выполнения можно зарегистрировать собственное расширение маршрутизации с новыми параметрами. В этом случае служба маршрутизации будет использовать обновленную конфигурацию для новых сеансов и сообщений (для уже запущенных на данных момент сообщений и сеансов будут применяться правила, действовавшие в момент их запуска).</span><span class="sxs-lookup"><span data-stu-id="12d2f-134">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="12d2f-135">Благодаря этому обеспечивается безопасная для сеансов и не требующая перезапуска повторная настройка службы маршрутизации во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="12d2f-135">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
  
