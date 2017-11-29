---
title: '&lt;mexHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4e8e9a13553e8b7463f7bb7f66c1a38dc1d4ac36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltmexhttpbindinggt"></a><span data-ttu-id="7069a-102">&lt;mexHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="7069a-102">&lt;mexHttpBinding&gt;</span></span>
<span data-ttu-id="7069a-103">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="7069a-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
 <span data-ttu-id="7069a-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7069a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7069a-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="7069a-105">\<bindings></span></span>  
<span data-ttu-id="7069a-106">\<mexHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="7069a-106">\<mexHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7069a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7069a-107">Syntax</span></span>  
  
```xml  
<mexHttpBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7069a-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7069a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7069a-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7069a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7069a-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7069a-110">Attributes</span></span>  
  
|<span data-ttu-id="7069a-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7069a-111">Attribute</span></span>|<span data-ttu-id="7069a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7069a-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="7069a-113">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="7069a-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="7069a-114">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7069a-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7069a-115">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="7069a-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="7069a-116">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="7069a-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="7069a-117">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="7069a-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="7069a-118">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="7069a-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="7069a-119">Кроме того, это имя является уникальным среди привязок одного типа.</span><span class="sxs-lookup"><span data-stu-id="7069a-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="7069a-120">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="7069a-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="7069a-121">Дополнительные сведения о конфигурации по умолчанию и безымянные привязок и поведений см. в разделе [упрощенной конфигурации](../../../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="7069a-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="7069a-122">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="7069a-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="7069a-123">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7069a-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7069a-124">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="7069a-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="7069a-125">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="7069a-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="7069a-126">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7069a-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7069a-127">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="7069a-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="7069a-128">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="7069a-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="7069a-129">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7069a-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7069a-130">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="7069a-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7069a-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7069a-131">Child Elements</span></span>  
 <span data-ttu-id="7069a-132">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7069a-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7069a-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7069a-133">Parent Elements</span></span>  
  
|<span data-ttu-id="7069a-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="7069a-134">Element</span></span>|<span data-ttu-id="7069a-135">Описание</span><span class="sxs-lookup"><span data-stu-id="7069a-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7069a-136">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="7069a-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="7069a-137">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="7069a-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7069a-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="7069a-138">Remarks</span></span>  
 <span data-ttu-id="7069a-139">Эта привязка по существу является привязкой `WSHttpBinding` с отключенной безопасностью.</span><span class="sxs-lookup"><span data-stu-id="7069a-139">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="7069a-140">Она поддерживает большинство запросов метаданных.</span><span class="sxs-lookup"><span data-stu-id="7069a-140">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7069a-141">См. также</span><span class="sxs-lookup"><span data-stu-id="7069a-141">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexHttpBindingElement>  
 [<span data-ttu-id="7069a-142">Как: публикация метаданных для службы с помощью файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="7069a-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="7069a-143">Публикация и получение метаданных через настраиваемую привязку.</span><span class="sxs-lookup"><span data-stu-id="7069a-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="7069a-144">Метаданные</span><span class="sxs-lookup"><span data-stu-id="7069a-144">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="7069a-145">Привязки</span><span class="sxs-lookup"><span data-stu-id="7069a-145">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="7069a-146">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="7069a-146">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="7069a-147">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="7069a-147">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="7069a-148">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="7069a-148">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
