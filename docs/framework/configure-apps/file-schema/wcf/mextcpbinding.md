---
title: '&lt;mexTcpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 518644e3fa60dd12c0fa86b246e3abfd5e4bfc80
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754562"
---
# <a name="ltmextcpbindinggt"></a><span data-ttu-id="14c4d-102">&lt;mexTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="14c4d-102">&lt;mexTcpBinding&gt;</span></span>
<span data-ttu-id="14c4d-103">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) по TCP.</span><span class="sxs-lookup"><span data-stu-id="14c4d-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
 <span data-ttu-id="14c4d-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="14c4d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="14c4d-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="14c4d-105">\<bindings></span></span>  
<span data-ttu-id="14c4d-106">\<mexTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="14c4d-106">\<mexTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14c4d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14c4d-107">Syntax</span></span>  
  
```xml  
<mexTcpBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14c4d-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="14c4d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="14c4d-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="14c4d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14c4d-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="14c4d-110">Attributes</span></span>  
  
|<span data-ttu-id="14c4d-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="14c4d-111">Attribute</span></span>|<span data-ttu-id="14c4d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="14c4d-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="14c4d-113">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="14c4d-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="14c4d-114">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="14c4d-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="14c4d-115">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="14c4d-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="14c4d-116">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="14c4d-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="14c4d-117">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="14c4d-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="14c4d-118">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="14c4d-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="14c4d-119">Кроме того, это имя является уникальным среди привязок одного типа.</span><span class="sxs-lookup"><span data-stu-id="14c4d-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="14c4d-120">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="14c4d-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="14c4d-121">Дополнительные сведения о конфигурации по умолчанию и безымянные привязок и поведений см. в разделе [упрощенной конфигурации](../../../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="14c4d-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="14c4d-122">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="14c4d-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="14c4d-123">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="14c4d-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="14c4d-124">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="14c4d-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="14c4d-125">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="14c4d-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="14c4d-126">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="14c4d-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="14c4d-127">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="14c4d-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="14c4d-128">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="14c4d-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="14c4d-129">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="14c4d-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="14c4d-130">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="14c4d-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14c4d-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="14c4d-131">Child Elements</span></span>  
 <span data-ttu-id="14c4d-132">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="14c4d-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14c4d-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="14c4d-133">Parent Elements</span></span>  
  
|<span data-ttu-id="14c4d-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="14c4d-134">Element</span></span>|<span data-ttu-id="14c4d-135">Описание</span><span class="sxs-lookup"><span data-stu-id="14c4d-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14c4d-136">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="14c4d-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="14c4d-137">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="14c4d-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14c4d-138">См. также</span><span class="sxs-lookup"><span data-stu-id="14c4d-138">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MexTcpBindingElement>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>  
 [<span data-ttu-id="14c4d-139">Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="14c4d-139">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="14c4d-140">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="14c4d-140">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="14c4d-141">Метаданные</span><span class="sxs-lookup"><span data-stu-id="14c4d-141">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="14c4d-142">Привязки</span><span class="sxs-lookup"><span data-stu-id="14c4d-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="14c4d-143">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="14c4d-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="14c4d-144">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="14c4d-144">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="14c4d-145">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="14c4d-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
