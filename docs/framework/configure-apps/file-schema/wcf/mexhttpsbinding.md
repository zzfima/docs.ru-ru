---
title: '&lt;mexHttpsBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4990965e364765628174f9e8765663c7a7df70d2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltmexhttpsbindinggt"></a><span data-ttu-id="74bd6-102">&lt;mexHttpsBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="74bd6-102">&lt;mexHttpsBinding&gt;</span></span>
<span data-ttu-id="74bd6-103">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) посредством HTTPS.</span><span class="sxs-lookup"><span data-stu-id="74bd6-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
 <span data-ttu-id="74bd6-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="74bd6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="74bd6-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="74bd6-105">\<bindings></span></span>  
<span data-ttu-id="74bd6-106">\<mexHttpsBinding ></span><span class="sxs-lookup"><span data-stu-id="74bd6-106">\<mexHttpsBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74bd6-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74bd6-107">Syntax</span></span>  
  
```xml  
<mexHttpsBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexHttpsBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74bd6-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="74bd6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="74bd6-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="74bd6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74bd6-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="74bd6-110">Attributes</span></span>  
  
|<span data-ttu-id="74bd6-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="74bd6-111">Attribute</span></span>|<span data-ttu-id="74bd6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="74bd6-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="74bd6-113">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="74bd6-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="74bd6-114">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="74bd6-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="74bd6-115">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="74bd6-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="74bd6-116">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="74bd6-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="74bd6-117">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="74bd6-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="74bd6-118">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="74bd6-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="74bd6-119">Кроме того, это имя является уникальным среди привязок одного типа.</span><span class="sxs-lookup"><span data-stu-id="74bd6-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="74bd6-120">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="74bd6-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="74bd6-121">Дополнительные сведения о конфигурации по умолчанию и безымянные привязок и поведений см. в разделе [упрощенной конфигурации](../../../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="74bd6-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="74bd6-122">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="74bd6-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="74bd6-123">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="74bd6-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="74bd6-124">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="74bd6-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="74bd6-125">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="74bd6-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="74bd6-126">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="74bd6-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="74bd6-127">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="74bd6-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="74bd6-128">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="74bd6-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="74bd6-129">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="74bd6-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="74bd6-130">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="74bd6-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74bd6-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="74bd6-131">Child Elements</span></span>  
 <span data-ttu-id="74bd6-132">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="74bd6-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74bd6-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="74bd6-133">Parent Elements</span></span>  
  
|<span data-ttu-id="74bd6-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="74bd6-134">Element</span></span>|<span data-ttu-id="74bd6-135">Описание</span><span class="sxs-lookup"><span data-stu-id="74bd6-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74bd6-136">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="74bd6-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="74bd6-137">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="74bd6-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74bd6-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="74bd6-138">Remarks</span></span>  
 <span data-ttu-id="74bd6-139">Эта привязка по существу является привязкой `WSHttpBinding`, которая поддерживает безопасность уровня транспорта с помощью сертификатов.</span><span class="sxs-lookup"><span data-stu-id="74bd6-139">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="74bd6-140">Дополнительные сведения о настройке и использовании такой конечной точки метаданных см. в разделе [как: Настройка пользовательских WS-Metadata Exchange привязка](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [как: получение метаданных через - MEX привязку, не](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)и Образец [конечной точки метаданных защиты пользовательских](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="74bd6-140">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74bd6-141">См. также</span><span class="sxs-lookup"><span data-stu-id="74bd6-141">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>  
 [<span data-ttu-id="74bd6-142">Как: публикация метаданных для службы с помощью файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="74bd6-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="74bd6-143">Публикация и получение метаданных через настраиваемую привязку.</span><span class="sxs-lookup"><span data-stu-id="74bd6-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="74bd6-144">Как: Настройка пользовательских WS-Metadata Exchange привязки</span><span class="sxs-lookup"><span data-stu-id="74bd6-144">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)  
 [<span data-ttu-id="74bd6-145">Как: - MEX привязку, не получить метаданные через</span><span class="sxs-lookup"><span data-stu-id="74bd6-145">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)  
 [<span data-ttu-id="74bd6-146">Пользовательские защищенной конечной точки метаданных</span><span class="sxs-lookup"><span data-stu-id="74bd6-146">Custom Secure Metadata Endpoint</span></span>](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)  
 [<span data-ttu-id="74bd6-147">Метаданные</span><span class="sxs-lookup"><span data-stu-id="74bd6-147">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="74bd6-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="74bd6-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="74bd6-149">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="74bd6-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="74bd6-150">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="74bd6-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="74bd6-151">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="74bd6-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
