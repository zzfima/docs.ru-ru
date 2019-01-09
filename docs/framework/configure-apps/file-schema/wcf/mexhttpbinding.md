---
title: '&lt;mexHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: c60fcf5071d52d30c1b6b99a19640a0fdc1265f8
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148660"
---
# <a name="ltmexhttpbindinggt"></a><span data-ttu-id="62b86-102">&lt;mexHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="62b86-102">&lt;mexHttpBinding&gt;</span></span>
<span data-ttu-id="62b86-103">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="62b86-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
 <span data-ttu-id="62b86-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="62b86-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="62b86-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="62b86-105">\<bindings></span></span>  
<span data-ttu-id="62b86-106">\<mexHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="62b86-106">\<mexHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62b86-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62b86-107">Syntax</span></span>  
  
```xml  
<mexHttpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62b86-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="62b86-108">Attributes and Elements</span></span>  
 <span data-ttu-id="62b86-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="62b86-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62b86-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="62b86-110">Attributes</span></span>  
  
|<span data-ttu-id="62b86-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="62b86-111">Attribute</span></span>|<span data-ttu-id="62b86-112">Описание</span><span class="sxs-lookup"><span data-stu-id="62b86-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="62b86-113">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="62b86-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="62b86-114">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="62b86-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="62b86-115">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="62b86-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="62b86-116">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="62b86-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="62b86-117">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="62b86-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="62b86-118">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="62b86-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="62b86-119">Кроме того, это имя является уникальным среди привязок одного типа.</span><span class="sxs-lookup"><span data-stu-id="62b86-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="62b86-120">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="62b86-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="62b86-121">Дополнительные сведения о конфигурации по умолчанию и безымянных привязках и поведениях см. в разделе [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="62b86-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="62b86-122">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="62b86-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="62b86-123">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="62b86-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="62b86-124">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="62b86-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="62b86-125">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="62b86-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="62b86-126">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="62b86-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="62b86-127">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="62b86-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="62b86-128">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="62b86-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="62b86-129">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="62b86-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="62b86-130">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="62b86-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62b86-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="62b86-131">Child Elements</span></span>  
 <span data-ttu-id="62b86-132">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="62b86-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62b86-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="62b86-133">Parent Elements</span></span>  
  
|<span data-ttu-id="62b86-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="62b86-134">Element</span></span>|<span data-ttu-id="62b86-135">Описание:</span><span class="sxs-lookup"><span data-stu-id="62b86-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62b86-136">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="62b86-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="62b86-137">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="62b86-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62b86-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="62b86-138">Remarks</span></span>  
 <span data-ttu-id="62b86-139">Эта привязка по существу является привязкой `WSHttpBinding` с отключенной безопасностью.</span><span class="sxs-lookup"><span data-stu-id="62b86-139">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="62b86-140">Она поддерживает большинство запросов метаданных.</span><span class="sxs-lookup"><span data-stu-id="62b86-140">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62b86-141">См. также</span><span class="sxs-lookup"><span data-stu-id="62b86-141">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexHttpBindingElement>  
 [<span data-ttu-id="62b86-142">Практическое руководство. Публикация метаданных для службы с помощью файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="62b86-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="62b86-143">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="62b86-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="62b86-144">Метаданные</span><span class="sxs-lookup"><span data-stu-id="62b86-144">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="62b86-145">Привязки</span><span class="sxs-lookup"><span data-stu-id="62b86-145">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="62b86-146">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="62b86-146">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="62b86-147">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="62b86-147">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="62b86-148">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="62b86-148">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
