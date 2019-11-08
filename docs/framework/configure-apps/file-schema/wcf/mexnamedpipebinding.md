---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: be538274636b519600d87b1d3be2faaa2e161cd0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738924"
---
# <a name="mexnamedpipebinding"></a><span data-ttu-id="3a647-101">\<Мекснамедпипебиндинг ></span><span class="sxs-lookup"><span data-stu-id="3a647-101">\<mexNamedPipeBinding></span></span>
<span data-ttu-id="3a647-102">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) посредством именованного канала.</span><span class="sxs-lookup"><span data-stu-id="3a647-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
<span data-ttu-id="3a647-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3a647-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3a647-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3a647-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3a647-105">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="3a647-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="3a647-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<мекснамедпипебиндинг >**</span><span class="sxs-lookup"><span data-stu-id="3a647-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexNamedPipeBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a647-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a647-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a647-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3a647-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3a647-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3a647-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a647-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3a647-110">Attributes</span></span>  
  
|<span data-ttu-id="3a647-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3a647-111">Attribute</span></span>|<span data-ttu-id="3a647-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3a647-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="3a647-113">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="3a647-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="3a647-114">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3a647-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3a647-115">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3a647-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="3a647-116">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="3a647-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="3a647-117">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="3a647-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="3a647-118">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="3a647-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="3a647-119">Кроме того, это имя является уникальным среди привязок одного типа.</span><span class="sxs-lookup"><span data-stu-id="3a647-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="3a647-120">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="3a647-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="3a647-121">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="3a647-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="3a647-122">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="3a647-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="3a647-123">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3a647-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3a647-124">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3a647-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="3a647-125">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="3a647-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="3a647-126">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3a647-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3a647-127">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="3a647-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="3a647-128">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="3a647-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="3a647-129">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3a647-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3a647-130">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3a647-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a647-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3a647-131">Child Elements</span></span>  
 <span data-ttu-id="3a647-132">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3a647-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a647-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3a647-133">Parent Elements</span></span>  
  
|<span data-ttu-id="3a647-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="3a647-134">Element</span></span>|<span data-ttu-id="3a647-135">Описание</span><span class="sxs-lookup"><span data-stu-id="3a647-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a647-136">привязки\<</span><span class="sxs-lookup"><span data-stu-id="3a647-136">\<bindings></span></span>](bindings.md)|<span data-ttu-id="3a647-137">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="3a647-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a647-138">См. также</span><span class="sxs-lookup"><span data-stu-id="3a647-138">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="3a647-139">Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="3a647-139">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="3a647-140">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="3a647-140">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="3a647-141">Метаданные</span><span class="sxs-lookup"><span data-stu-id="3a647-141">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="3a647-142">Привязки</span><span class="sxs-lookup"><span data-stu-id="3a647-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3a647-143">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="3a647-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3a647-144">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="3a647-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="3a647-145">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="3a647-145">\<binding></span></span>](bindings.md)
