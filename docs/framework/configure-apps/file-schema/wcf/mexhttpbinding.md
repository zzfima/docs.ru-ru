---
title: <mexHttpBinding>
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: 8a8145bbfcb3eefb06d159d834232d94166fa6dd
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736715"
---
# <a name="mexhttpbinding"></a><span data-ttu-id="9de6b-101">\<Мексхттпбиндинг ></span><span class="sxs-lookup"><span data-stu-id="9de6b-101">\<mexHttpBinding></span></span>
<span data-ttu-id="9de6b-102">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="9de6b-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
<span data-ttu-id="9de6b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9de6b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9de6b-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9de6b-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9de6b-105">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="9de6b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="9de6b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<мексхттпбиндинг >**</span><span class="sxs-lookup"><span data-stu-id="9de6b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9de6b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9de6b-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9de6b-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9de6b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9de6b-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9de6b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9de6b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9de6b-110">Attributes</span></span>  
  
|<span data-ttu-id="9de6b-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9de6b-111">Attribute</span></span>|<span data-ttu-id="9de6b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9de6b-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="9de6b-113">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="9de6b-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="9de6b-114">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="9de6b-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9de6b-115">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="9de6b-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="9de6b-116">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="9de6b-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="9de6b-117">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="9de6b-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="9de6b-118">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="9de6b-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="9de6b-119">Кроме того, это имя является уникальным среди привязок одного типа.</span><span class="sxs-lookup"><span data-stu-id="9de6b-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="9de6b-120">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="9de6b-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="9de6b-121">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="9de6b-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="9de6b-122">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="9de6b-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="9de6b-123">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="9de6b-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9de6b-124">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="9de6b-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="9de6b-125">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="9de6b-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="9de6b-126">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="9de6b-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9de6b-127">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="9de6b-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="9de6b-128">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="9de6b-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="9de6b-129">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="9de6b-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9de6b-130">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="9de6b-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9de6b-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9de6b-131">Child Elements</span></span>  
 <span data-ttu-id="9de6b-132">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9de6b-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9de6b-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9de6b-133">Parent Elements</span></span>  
  
|<span data-ttu-id="9de6b-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="9de6b-134">Element</span></span>|<span data-ttu-id="9de6b-135">Описание</span><span class="sxs-lookup"><span data-stu-id="9de6b-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9de6b-136">привязки\<</span><span class="sxs-lookup"><span data-stu-id="9de6b-136">\<bindings></span></span>](bindings.md)|<span data-ttu-id="9de6b-137">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="9de6b-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9de6b-138">Заметки</span><span class="sxs-lookup"><span data-stu-id="9de6b-138">Remarks</span></span>  
 <span data-ttu-id="9de6b-139">Эта привязка по существу является привязкой `WSHttpBinding` с отключенной безопасностью.</span><span class="sxs-lookup"><span data-stu-id="9de6b-139">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="9de6b-140">Она поддерживает большинство запросов метаданных.</span><span class="sxs-lookup"><span data-stu-id="9de6b-140">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9de6b-141">См. также</span><span class="sxs-lookup"><span data-stu-id="9de6b-141">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpBindingElement>
- [<span data-ttu-id="9de6b-142">Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="9de6b-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="9de6b-143">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="9de6b-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="9de6b-144">Метаданные</span><span class="sxs-lookup"><span data-stu-id="9de6b-144">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="9de6b-145">Привязки</span><span class="sxs-lookup"><span data-stu-id="9de6b-145">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9de6b-146">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="9de6b-146">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9de6b-147">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="9de6b-147">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9de6b-148">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="9de6b-148">\<binding></span></span>](bindings.md)
