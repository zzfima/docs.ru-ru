---
title: '&lt;mexNamedPipeBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e786d2f18fca2b04e0a46536e539895890fc67d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltmexnamedpipebindinggt"></a><span data-ttu-id="01bc2-102">&lt;mexNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="01bc2-102">&lt;mexNamedPipeBinding&gt;</span></span>
<span data-ttu-id="01bc2-103">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) посредством именованного канала.</span><span class="sxs-lookup"><span data-stu-id="01bc2-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
 <span data-ttu-id="01bc2-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="01bc2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="01bc2-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="01bc2-105">\<bindings></span></span>  
<span data-ttu-id="01bc2-106">\<mexNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="01bc2-106">\<mexNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01bc2-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01bc2-107">Syntax</span></span>  
  
```xml  
<mexNamedPipeBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01bc2-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="01bc2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="01bc2-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="01bc2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01bc2-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="01bc2-110">Attributes</span></span>  
  
|<span data-ttu-id="01bc2-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="01bc2-111">Attribute</span></span>|<span data-ttu-id="01bc2-112">Описание</span><span class="sxs-lookup"><span data-stu-id="01bc2-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="01bc2-113">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="01bc2-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="01bc2-114">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="01bc2-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="01bc2-115">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="01bc2-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="01bc2-116">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="01bc2-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="01bc2-117">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="01bc2-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="01bc2-118">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="01bc2-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="01bc2-119">Кроме того, это имя является уникальным среди привязок одного типа.</span><span class="sxs-lookup"><span data-stu-id="01bc2-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="01bc2-120">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="01bc2-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="01bc2-121">Дополнительные сведения о конфигурации по умолчанию и безымянные привязок и поведений см. в разделе [упрощенной конфигурации](../../../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="01bc2-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="01bc2-122">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="01bc2-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="01bc2-123">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="01bc2-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="01bc2-124">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="01bc2-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="01bc2-125">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="01bc2-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="01bc2-126">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="01bc2-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="01bc2-127">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="01bc2-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="01bc2-128">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="01bc2-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="01bc2-129">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="01bc2-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="01bc2-130">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="01bc2-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01bc2-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="01bc2-131">Child Elements</span></span>  
 <span data-ttu-id="01bc2-132">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="01bc2-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01bc2-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="01bc2-133">Parent Elements</span></span>  
  
|<span data-ttu-id="01bc2-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="01bc2-134">Element</span></span>|<span data-ttu-id="01bc2-135">Описание</span><span class="sxs-lookup"><span data-stu-id="01bc2-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01bc2-136">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="01bc2-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="01bc2-137">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="01bc2-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01bc2-138">См. также</span><span class="sxs-lookup"><span data-stu-id="01bc2-138">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>  
 [<span data-ttu-id="01bc2-139">Как: публикация метаданных для службы с помощью файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="01bc2-139">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="01bc2-140">Публикация и получение метаданных через настраиваемую привязку.</span><span class="sxs-lookup"><span data-stu-id="01bc2-140">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="01bc2-141">Метаданные</span><span class="sxs-lookup"><span data-stu-id="01bc2-141">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="01bc2-142">Привязки</span><span class="sxs-lookup"><span data-stu-id="01bc2-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="01bc2-143">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="01bc2-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="01bc2-144">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="01bc2-144">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="01bc2-145">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="01bc2-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
