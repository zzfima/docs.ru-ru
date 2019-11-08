---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 79c3c68d69bf3cf5a018e6cf62f34e5ec2ce0cd5
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738938"
---
# <a name="mexhttpsbinding"></a><span data-ttu-id="8371a-101">\<Мексхттпсбиндинг ></span><span class="sxs-lookup"><span data-stu-id="8371a-101">\<mexHttpsBinding></span></span>
<span data-ttu-id="8371a-102">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) посредством HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8371a-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
<span data-ttu-id="8371a-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8371a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8371a-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8371a-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8371a-105">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="8371a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="8371a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<мексхттпсбиндинг >**</span><span class="sxs-lookup"><span data-stu-id="8371a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpsBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8371a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8371a-107">Syntax</span></span>  
  
```xml  
<mexHttpsBinding>
  <binding closeTimeout="TimeSpan"
            name="string"
            openTimeout="TimeSpan"
            receiveTimeout="TimeSpan"
            sendTimeout="TimeSpan">
  </binding>
</mexHttpsBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8371a-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8371a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8371a-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8371a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8371a-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8371a-110">Attributes</span></span>  
  
|<span data-ttu-id="8371a-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8371a-111">Attribute</span></span>|<span data-ttu-id="8371a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8371a-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="8371a-113">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="8371a-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="8371a-114">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="8371a-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8371a-115">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="8371a-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="8371a-116">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="8371a-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="8371a-117">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="8371a-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="8371a-118">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="8371a-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="8371a-119">Кроме того, это имя является уникальным среди привязок одного типа.</span><span class="sxs-lookup"><span data-stu-id="8371a-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="8371a-120">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="8371a-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="8371a-121">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="8371a-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="8371a-122">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="8371a-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="8371a-123">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="8371a-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8371a-124">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="8371a-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="8371a-125">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="8371a-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="8371a-126">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="8371a-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8371a-127">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="8371a-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="8371a-128">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="8371a-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="8371a-129">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="8371a-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8371a-130">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="8371a-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8371a-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8371a-131">Child Elements</span></span>  
 <span data-ttu-id="8371a-132">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8371a-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8371a-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8371a-133">Parent Elements</span></span>  
  
|<span data-ttu-id="8371a-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="8371a-134">Element</span></span>|<span data-ttu-id="8371a-135">Описание</span><span class="sxs-lookup"><span data-stu-id="8371a-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8371a-136">привязки\<</span><span class="sxs-lookup"><span data-stu-id="8371a-136">\<bindings></span></span>](bindings.md)|<span data-ttu-id="8371a-137">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="8371a-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8371a-138">Заметки</span><span class="sxs-lookup"><span data-stu-id="8371a-138">Remarks</span></span>  
 <span data-ttu-id="8371a-139">Эта привязка по существу является привязкой `WSHttpBinding`, которая поддерживает безопасность уровня транспорта с помощью сертификатов.</span><span class="sxs-lookup"><span data-stu-id="8371a-139">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="8371a-140">Дополнительные сведения о настройке и использовании такой конечной точки метаданных см. в разделе [как настроить настраиваемую привязку WS-Metadata Exchange](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [как получать метаданные через привязку обмена метаданными](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), а также образец [настраиваемой конечной точки безопасных метаданных](../../../wcf/samples/custom-secure-metadata-endpoint.md) . .</span><span class="sxs-lookup"><span data-stu-id="8371a-140">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8371a-141">См. также</span><span class="sxs-lookup"><span data-stu-id="8371a-141">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="8371a-142">Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="8371a-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="8371a-143">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="8371a-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="8371a-144">Практическое руководство. Настройка пользовательской привязки WS-Metadata Exchange</span><span class="sxs-lookup"><span data-stu-id="8371a-144">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="8371a-145">Практическое руководство. Получение метаданных через привязку, не использующую MEX</span><span class="sxs-lookup"><span data-stu-id="8371a-145">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="8371a-146">Пользовательская конечная точка защищенных метаданных</span><span class="sxs-lookup"><span data-stu-id="8371a-146">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="8371a-147">Метаданные</span><span class="sxs-lookup"><span data-stu-id="8371a-147">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="8371a-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="8371a-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8371a-149">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="8371a-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8371a-150">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="8371a-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8371a-151">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="8371a-151">\<binding></span></span>](bindings.md)
