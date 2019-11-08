---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 91c1d17ef450200c95d7f871e8cbee85ddd260d1
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738906"
---
# <a name="mextcpbinding"></a><span data-ttu-id="d980f-101">\<Мексткпбиндинг ></span><span class="sxs-lookup"><span data-stu-id="d980f-101">\<mexTcpBinding></span></span>
<span data-ttu-id="d980f-102">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) по TCP.</span><span class="sxs-lookup"><span data-stu-id="d980f-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
<span data-ttu-id="d980f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d980f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d980f-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d980f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d980f-105">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="d980f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="d980f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<мексткпбиндинг >**</span><span class="sxs-lookup"><span data-stu-id="d980f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexTcpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d980f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d980f-107">Syntax</span></span>  
  
```xml  
<mexTcpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d980f-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d980f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d980f-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d980f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d980f-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d980f-110">Attributes</span></span>  
  
|<span data-ttu-id="d980f-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d980f-111">Attribute</span></span>|<span data-ttu-id="d980f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d980f-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="d980f-113">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="d980f-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="d980f-114">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d980f-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d980f-115">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d980f-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="d980f-116">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="d980f-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="d980f-117">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="d980f-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="d980f-118">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="d980f-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="d980f-119">Кроме того, это имя является уникальным среди привязок одного типа.</span><span class="sxs-lookup"><span data-stu-id="d980f-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="d980f-120">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="d980f-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="d980f-121">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="d980f-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="d980f-122">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="d980f-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="d980f-123">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d980f-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d980f-124">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d980f-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="d980f-125">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="d980f-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="d980f-126">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d980f-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d980f-127">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="d980f-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="d980f-128">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="d980f-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="d980f-129">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="d980f-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="d980f-130">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="d980f-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d980f-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d980f-131">Child Elements</span></span>  
 <span data-ttu-id="d980f-132">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d980f-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d980f-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d980f-133">Parent Elements</span></span>  
  
|<span data-ttu-id="d980f-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="d980f-134">Element</span></span>|<span data-ttu-id="d980f-135">Описание</span><span class="sxs-lookup"><span data-stu-id="d980f-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d980f-136">привязки\<</span><span class="sxs-lookup"><span data-stu-id="d980f-136">\<bindings></span></span>](bindings.md)|<span data-ttu-id="d980f-137">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="d980f-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d980f-138">См. также</span><span class="sxs-lookup"><span data-stu-id="d980f-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="d980f-139">Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="d980f-139">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="d980f-140">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="d980f-140">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="d980f-141">Метаданные</span><span class="sxs-lookup"><span data-stu-id="d980f-141">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="d980f-142">Привязки</span><span class="sxs-lookup"><span data-stu-id="d980f-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d980f-143">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="d980f-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d980f-144">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="d980f-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d980f-145">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="d980f-145">\<binding></span></span>](bindings.md)
