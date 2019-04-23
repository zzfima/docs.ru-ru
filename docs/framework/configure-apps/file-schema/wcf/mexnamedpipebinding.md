---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: 9ac2b967e33571cbe0b4ad5ee81e13b009ffddd3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111368"
---
# <a name="mexnamedpipebinding"></a><span data-ttu-id="d58d2-101">\<mexNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="d58d2-101">\<mexNamedPipeBinding></span></span>
<span data-ttu-id="d58d2-102">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) посредством именованного канала.</span><span class="sxs-lookup"><span data-stu-id="d58d2-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
 <span data-ttu-id="d58d2-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d58d2-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d58d2-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="d58d2-104">\<bindings></span></span>  
<span data-ttu-id="d58d2-105">\<mexNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="d58d2-105">\<mexNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d58d2-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d58d2-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d58d2-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d58d2-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d58d2-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d58d2-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d58d2-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d58d2-109">Attributes</span></span>  
  
|<span data-ttu-id="d58d2-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d58d2-110">Attribute</span></span>|<span data-ttu-id="d58d2-111">Описание</span><span class="sxs-lookup"><span data-stu-id="d58d2-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="d58d2-112">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="d58d2-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="d58d2-113">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d58d2-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d58d2-114">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d58d2-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="d58d2-115">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="d58d2-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="d58d2-116">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="d58d2-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="d58d2-117">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="d58d2-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="d58d2-118">Кроме того, это имя является уникальным среди привязок одного типа.</span><span class="sxs-lookup"><span data-stu-id="d58d2-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="d58d2-119">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="d58d2-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="d58d2-120">Дополнительные сведения о конфигурации по умолчанию и безымянных привязках и поведениях см. в разделе [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="d58d2-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="d58d2-121">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="d58d2-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="d58d2-122">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d58d2-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d58d2-123">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d58d2-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="d58d2-124">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="d58d2-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="d58d2-125">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d58d2-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d58d2-126">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="d58d2-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="d58d2-127">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="d58d2-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="d58d2-128">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d58d2-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d58d2-129">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d58d2-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d58d2-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d58d2-130">Child Elements</span></span>  
 <span data-ttu-id="d58d2-131">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d58d2-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d58d2-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d58d2-132">Parent Elements</span></span>  
  
|<span data-ttu-id="d58d2-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="d58d2-133">Element</span></span>|<span data-ttu-id="d58d2-134">Описание</span><span class="sxs-lookup"><span data-stu-id="d58d2-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d58d2-135">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="d58d2-135">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="d58d2-136">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="d58d2-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d58d2-137">См. также</span><span class="sxs-lookup"><span data-stu-id="d58d2-137">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="d58d2-138">Практическое руководство. Публикация метаданных для службы с помощью файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="d58d2-138">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="d58d2-139">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="d58d2-139">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="d58d2-140">Метаданные</span><span class="sxs-lookup"><span data-stu-id="d58d2-140">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="d58d2-141">Привязки</span><span class="sxs-lookup"><span data-stu-id="d58d2-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="d58d2-142">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="d58d2-142">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d58d2-143">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="d58d2-143">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d58d2-144">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="d58d2-144">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
