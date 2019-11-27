---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 8d0ae2a1848eaf28c2e408542b8209cf968de4c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430300"
---
# <a name="mextcpbinding"></a><span data-ttu-id="ecdfd-101">\<Мексткпбиндинг ></span><span class="sxs-lookup"><span data-stu-id="ecdfd-101">\<mexTcpBinding></span></span>
<span data-ttu-id="ecdfd-102">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) по TCP.</span><span class="sxs-lookup"><span data-stu-id="ecdfd-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
<span data-ttu-id="ecdfd-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ecdfd-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ecdfd-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ecdfd-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ecdfd-105">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="ecdfd-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="ecdfd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<мексткпбиндинг >**</span><span class="sxs-lookup"><span data-stu-id="ecdfd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexTcpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecdfd-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ecdfd-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ecdfd-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ecdfd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ecdfd-109">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ecdfd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ecdfd-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ecdfd-110">Attributes</span></span>  
  
|<span data-ttu-id="ecdfd-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ecdfd-111">Attribute</span></span>|<span data-ttu-id="ecdfd-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ecdfd-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="ecdfd-113">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="ecdfd-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="ecdfd-114">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ecdfd-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ecdfd-115">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ecdfd-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="ecdfd-116">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="ecdfd-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="ecdfd-117">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="ecdfd-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="ecdfd-118">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="ecdfd-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="ecdfd-119">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="ecdfd-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="ecdfd-120">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="ecdfd-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="ecdfd-121">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ecdfd-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ecdfd-122">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ecdfd-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="ecdfd-123">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="ecdfd-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="ecdfd-124">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ecdfd-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ecdfd-125">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="ecdfd-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="ecdfd-126">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="ecdfd-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="ecdfd-127">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ecdfd-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ecdfd-128">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ecdfd-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ecdfd-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ecdfd-129">Child Elements</span></span>  
 <span data-ttu-id="ecdfd-130">Нет</span><span class="sxs-lookup"><span data-stu-id="ecdfd-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ecdfd-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ecdfd-131">Parent Elements</span></span>  
  
|<span data-ttu-id="ecdfd-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="ecdfd-132">Element</span></span>|<span data-ttu-id="ecdfd-133">Описание</span><span class="sxs-lookup"><span data-stu-id="ecdfd-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ecdfd-134">привязки \<></span><span class="sxs-lookup"><span data-stu-id="ecdfd-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="ecdfd-135">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="ecdfd-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ecdfd-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="ecdfd-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="ecdfd-137">Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="ecdfd-137">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="ecdfd-138">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="ecdfd-138">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="ecdfd-139">Метаданные</span><span class="sxs-lookup"><span data-stu-id="ecdfd-139">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="ecdfd-140">Привязки</span><span class="sxs-lookup"><span data-stu-id="ecdfd-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ecdfd-141">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="ecdfd-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ecdfd-142">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="ecdfd-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ecdfd-143">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="ecdfd-143">\<binding></span></span>](bindings.md)
