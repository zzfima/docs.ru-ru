---
title: <mexHttpBinding>
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: 8d5b9378bf7769754586d0b13f742659aee18f03
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430912"
---
# <a name="mexhttpbinding"></a><span data-ttu-id="a94d9-101">\<mexHttpBinding></span><span class="sxs-lookup"><span data-stu-id="a94d9-101">\<mexHttpBinding></span></span>
<span data-ttu-id="a94d9-102">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="a94d9-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
<span data-ttu-id="a94d9-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a94d9-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a94d9-104">&nbsp;&nbsp;[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a94d9-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a94d9-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bindings>** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a94d9-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="a94d9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexHttpBinding>**</span><span class="sxs-lookup"><span data-stu-id="a94d9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a94d9-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a94d9-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a94d9-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a94d9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a94d9-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a94d9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a94d9-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a94d9-110">Attributes</span></span>  
  
|<span data-ttu-id="a94d9-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a94d9-111">Attribute</span></span>|<span data-ttu-id="a94d9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a94d9-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="a94d9-113">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="a94d9-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="a94d9-114">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a94d9-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a94d9-115">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a94d9-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="a94d9-116">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="a94d9-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="a94d9-117">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="a94d9-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="a94d9-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span><span class="sxs-lookup"><span data-stu-id="a94d9-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="a94d9-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="a94d9-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="a94d9-120">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="a94d9-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="a94d9-121">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a94d9-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a94d9-122">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a94d9-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="a94d9-123">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="a94d9-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="a94d9-124">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a94d9-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a94d9-125">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="a94d9-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="a94d9-126">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="a94d9-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="a94d9-127">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a94d9-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a94d9-128">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a94d9-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a94d9-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a94d9-129">Child Elements</span></span>  
 <span data-ttu-id="a94d9-130">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a94d9-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a94d9-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a94d9-131">Parent Elements</span></span>  
  
|<span data-ttu-id="a94d9-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="a94d9-132">Element</span></span>|<span data-ttu-id="a94d9-133">Описание</span><span class="sxs-lookup"><span data-stu-id="a94d9-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a94d9-134">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a94d9-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="a94d9-135">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="a94d9-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a94d9-136">Заметки</span><span class="sxs-lookup"><span data-stu-id="a94d9-136">Remarks</span></span>  
 <span data-ttu-id="a94d9-137">Эта привязка по существу является привязкой `WSHttpBinding` с отключенной безопасностью.</span><span class="sxs-lookup"><span data-stu-id="a94d9-137">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="a94d9-138">Она поддерживает большинство запросов метаданных.</span><span class="sxs-lookup"><span data-stu-id="a94d9-138">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a94d9-139">См. также</span><span class="sxs-lookup"><span data-stu-id="a94d9-139">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpBindingElement>
- [<span data-ttu-id="a94d9-140">Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="a94d9-140">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="a94d9-141">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="a94d9-141">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="a94d9-142">Метаданные</span><span class="sxs-lookup"><span data-stu-id="a94d9-142">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="a94d9-143">Привязки</span><span class="sxs-lookup"><span data-stu-id="a94d9-143">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a94d9-144">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="a94d9-144">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a94d9-145">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="a94d9-145">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a94d9-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="a94d9-146">\<binding></span></span>](bindings.md)
