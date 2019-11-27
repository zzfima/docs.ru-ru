---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: 41f5b19f5067d9ac7faa2c7329dd07dd9d48e9b3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430871"
---
# <a name="mexnamedpipebinding"></a><span data-ttu-id="18dec-101">\<Мекснамедпипебиндинг ></span><span class="sxs-lookup"><span data-stu-id="18dec-101">\<mexNamedPipeBinding></span></span>
<span data-ttu-id="18dec-102">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) посредством именованного канала.</span><span class="sxs-lookup"><span data-stu-id="18dec-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
<span data-ttu-id="18dec-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="18dec-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="18dec-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="18dec-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="18dec-105">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="18dec-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="18dec-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<мекснамедпипебиндинг >**</span><span class="sxs-lookup"><span data-stu-id="18dec-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexNamedPipeBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18dec-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18dec-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18dec-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="18dec-108">Attributes and Elements</span></span>  
 <span data-ttu-id="18dec-109">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="18dec-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18dec-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="18dec-110">Attributes</span></span>  
  
|<span data-ttu-id="18dec-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="18dec-111">Attribute</span></span>|<span data-ttu-id="18dec-112">Описание</span><span class="sxs-lookup"><span data-stu-id="18dec-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="18dec-113">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="18dec-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="18dec-114">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="18dec-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="18dec-115">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="18dec-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="18dec-116">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="18dec-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="18dec-117">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="18dec-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="18dec-118">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="18dec-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="18dec-119">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="18dec-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="18dec-120">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="18dec-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="18dec-121">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="18dec-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="18dec-122">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="18dec-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="18dec-123">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="18dec-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="18dec-124">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="18dec-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="18dec-125">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="18dec-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="18dec-126">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="18dec-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="18dec-127">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="18dec-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="18dec-128">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="18dec-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18dec-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="18dec-129">Child Elements</span></span>  
 <span data-ttu-id="18dec-130">Нет</span><span class="sxs-lookup"><span data-stu-id="18dec-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18dec-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="18dec-131">Parent Elements</span></span>  
  
|<span data-ttu-id="18dec-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="18dec-132">Element</span></span>|<span data-ttu-id="18dec-133">Описание</span><span class="sxs-lookup"><span data-stu-id="18dec-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18dec-134">привязки \<></span><span class="sxs-lookup"><span data-stu-id="18dec-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="18dec-135">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="18dec-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18dec-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="18dec-136">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="18dec-137">Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="18dec-137">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="18dec-138">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="18dec-138">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="18dec-139">Метаданные</span><span class="sxs-lookup"><span data-stu-id="18dec-139">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="18dec-140">Привязки</span><span class="sxs-lookup"><span data-stu-id="18dec-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="18dec-141">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="18dec-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="18dec-142">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="18dec-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="18dec-143">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="18dec-143">\<binding></span></span>](bindings.md)
