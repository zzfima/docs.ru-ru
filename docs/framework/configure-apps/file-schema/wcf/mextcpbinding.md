---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: d77809ae87a28995b3f37848e19ebddd24942f22
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397753"
---
# <a name="mextcpbinding"></a><span data-ttu-id="32b79-101">\<Мексткпбиндинг ></span><span class="sxs-lookup"><span data-stu-id="32b79-101">\<mexTcpBinding></span></span>
<span data-ttu-id="32b79-102">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) по TCP.</span><span class="sxs-lookup"><span data-stu-id="32b79-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
<span data-ttu-id="32b79-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="32b79-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="32b79-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="32b79-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="32b79-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="32b79-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="32b79-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Мексткпбиндинг >**</span><span class="sxs-lookup"><span data-stu-id="32b79-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexTcpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32b79-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32b79-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32b79-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="32b79-108">Attributes and Elements</span></span>  
 <span data-ttu-id="32b79-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="32b79-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32b79-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="32b79-110">Attributes</span></span>  
  
|<span data-ttu-id="32b79-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="32b79-111">Attribute</span></span>|<span data-ttu-id="32b79-112">Описание</span><span class="sxs-lookup"><span data-stu-id="32b79-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="32b79-113">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="32b79-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="32b79-114">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="32b79-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="32b79-115">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="32b79-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="32b79-116">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="32b79-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="32b79-117">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="32b79-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="32b79-118">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="32b79-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="32b79-119">Кроме того, это имя является уникальным среди привязок одного типа.</span><span class="sxs-lookup"><span data-stu-id="32b79-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="32b79-120">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="32b79-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="32b79-121">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="32b79-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="32b79-122">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="32b79-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="32b79-123">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="32b79-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="32b79-124">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="32b79-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="32b79-125">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="32b79-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="32b79-126">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="32b79-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="32b79-127">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="32b79-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="32b79-128">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="32b79-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="32b79-129">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="32b79-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="32b79-130">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="32b79-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32b79-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="32b79-131">Child Elements</span></span>  
 <span data-ttu-id="32b79-132">Нет.</span><span class="sxs-lookup"><span data-stu-id="32b79-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32b79-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="32b79-133">Parent Elements</span></span>  
  
|<span data-ttu-id="32b79-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="32b79-134">Element</span></span>|<span data-ttu-id="32b79-135">Описание</span><span class="sxs-lookup"><span data-stu-id="32b79-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32b79-136">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="32b79-136">\<bindings></span></span>](bindings.md)|<span data-ttu-id="32b79-137">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="32b79-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32b79-138">См. также</span><span class="sxs-lookup"><span data-stu-id="32b79-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="32b79-139">Практическое руководство. Публикация метаданных для службы с помощью файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="32b79-139">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="32b79-140">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="32b79-140">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="32b79-141">Метаданные</span><span class="sxs-lookup"><span data-stu-id="32b79-141">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="32b79-142">Привязки</span><span class="sxs-lookup"><span data-stu-id="32b79-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="32b79-143">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="32b79-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="32b79-144">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="32b79-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="32b79-145">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="32b79-145">\<binding></span></span>](../../../misc/binding.md)
