---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: 0d0904c02e31def1b5264bec9f61eac0c9a8e964
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931235"
---
# <a name="mexnamedpipebinding"></a><span data-ttu-id="e3bd6-101">\<Мекснамедпипебиндинг ></span><span class="sxs-lookup"><span data-stu-id="e3bd6-101">\<mexNamedPipeBinding></span></span>
<span data-ttu-id="e3bd6-102">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) посредством именованного канала.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
 <span data-ttu-id="e3bd6-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e3bd6-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e3bd6-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="e3bd6-104">\<bindings></span></span>  
<span data-ttu-id="e3bd6-105">\<Мекснамедпипебиндинг ></span><span class="sxs-lookup"><span data-stu-id="e3bd6-105">\<mexNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3bd6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3bd6-106">Syntax</span></span>  
  
```xml  
<mexNamedPipeBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3bd6-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e3bd6-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e3bd6-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3bd6-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e3bd6-109">Attributes</span></span>  
  
|<span data-ttu-id="e3bd6-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e3bd6-110">Attribute</span></span>|<span data-ttu-id="e3bd6-111">Описание</span><span class="sxs-lookup"><span data-stu-id="e3bd6-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="e3bd6-112">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="e3bd6-113">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e3bd6-114">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="e3bd6-115">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="e3bd6-116">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="e3bd6-117">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="e3bd6-118">Кроме того, это имя является уникальным среди привязок одного типа.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="e3bd6-119">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="e3bd6-120">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="e3bd6-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="e3bd6-121">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="e3bd6-122">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e3bd6-123">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="e3bd6-124">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="e3bd6-125">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e3bd6-126">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="e3bd6-127">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="e3bd6-128">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e3bd6-129">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3bd6-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e3bd6-130">Child Elements</span></span>  
 <span data-ttu-id="e3bd6-131">Нет.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e3bd6-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e3bd6-132">Parent Elements</span></span>  
  
|<span data-ttu-id="e3bd6-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3bd6-133">Element</span></span>|<span data-ttu-id="e3bd6-134">Описание</span><span class="sxs-lookup"><span data-stu-id="e3bd6-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3bd6-135">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="e3bd6-135">\<bindings></span></span>](bindings.md)|<span data-ttu-id="e3bd6-136">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="e3bd6-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3bd6-137">См. также</span><span class="sxs-lookup"><span data-stu-id="e3bd6-137">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="e3bd6-138">Практическое руководство. Публикация метаданных для службы с помощью файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e3bd6-138">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="e3bd6-139">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="e3bd6-139">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="e3bd6-140">Метаданные</span><span class="sxs-lookup"><span data-stu-id="e3bd6-140">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="e3bd6-141">Привязки</span><span class="sxs-lookup"><span data-stu-id="e3bd6-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e3bd6-142">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="e3bd6-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e3bd6-143">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e3bd6-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e3bd6-144">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="e3bd6-144">\<binding></span></span>](../../../misc/binding.md)
