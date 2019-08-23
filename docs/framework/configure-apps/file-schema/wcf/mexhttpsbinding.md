---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 30d1aa27ce29b6aa4091c3e7be05746ad462102a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931272"
---
# <a name="mexhttpsbinding"></a><span data-ttu-id="a46d9-101">\<Мексхттпсбиндинг ></span><span class="sxs-lookup"><span data-stu-id="a46d9-101">\<mexHttpsBinding></span></span>
<span data-ttu-id="a46d9-102">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) посредством HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a46d9-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
 <span data-ttu-id="a46d9-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a46d9-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a46d9-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="a46d9-104">\<bindings></span></span>  
<span data-ttu-id="a46d9-105">\<Мексхттпсбиндинг ></span><span class="sxs-lookup"><span data-stu-id="a46d9-105">\<mexHttpsBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a46d9-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a46d9-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a46d9-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a46d9-107">Attributes and Elements</span></span>  
 <span data-ttu-id="a46d9-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a46d9-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a46d9-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a46d9-109">Attributes</span></span>  
  
|<span data-ttu-id="a46d9-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a46d9-110">Attribute</span></span>|<span data-ttu-id="a46d9-111">Описание</span><span class="sxs-lookup"><span data-stu-id="a46d9-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="a46d9-112">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="a46d9-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="a46d9-113">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a46d9-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a46d9-114">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a46d9-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="a46d9-115">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="a46d9-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="a46d9-116">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="a46d9-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="a46d9-117">Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="a46d9-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="a46d9-118">Кроме того, это имя является уникальным среди привязок одного типа.</span><span class="sxs-lookup"><span data-stu-id="a46d9-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="a46d9-119">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="a46d9-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="a46d9-120">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="a46d9-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="a46d9-121">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="a46d9-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="a46d9-122">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a46d9-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a46d9-123">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a46d9-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="a46d9-124">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="a46d9-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="a46d9-125">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a46d9-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a46d9-126">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="a46d9-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="a46d9-127">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="a46d9-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="a46d9-128">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a46d9-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a46d9-129">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a46d9-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a46d9-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a46d9-130">Child Elements</span></span>  
 <span data-ttu-id="a46d9-131">Нет.</span><span class="sxs-lookup"><span data-stu-id="a46d9-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a46d9-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a46d9-132">Parent Elements</span></span>  
  
|<span data-ttu-id="a46d9-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="a46d9-133">Element</span></span>|<span data-ttu-id="a46d9-134">Описание</span><span class="sxs-lookup"><span data-stu-id="a46d9-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a46d9-135">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="a46d9-135">\<bindings></span></span>](bindings.md)|<span data-ttu-id="a46d9-136">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="a46d9-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a46d9-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="a46d9-137">Remarks</span></span>  
 <span data-ttu-id="a46d9-138">Эта привязка по существу является привязкой `WSHttpBinding`, которая поддерживает безопасность уровня транспорта с помощью сертификатов.</span><span class="sxs-lookup"><span data-stu-id="a46d9-138">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="a46d9-139">Дополнительные сведения о настройке и использовании такой конечной точки метаданных см. в [разделе как Настройка пользовательской привязки](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)WS-Metadata Exchange, [а именно: Получение метаданных по привязке](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)без обмена метаданными и пример [пользовательской защищенной конечной точки метаданных](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="a46d9-139">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a46d9-140">См. также</span><span class="sxs-lookup"><span data-stu-id="a46d9-140">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="a46d9-141">Практическое руководство. Публикация метаданных для службы с помощью файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="a46d9-141">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="a46d9-142">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="a46d9-142">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="a46d9-143">Практическое руководство. Настройка пользовательской привязки WS-Metadata Exchange</span><span class="sxs-lookup"><span data-stu-id="a46d9-143">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="a46d9-144">Практическое руководство. Получение метаданных по привязке без обмена метаданными</span><span class="sxs-lookup"><span data-stu-id="a46d9-144">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="a46d9-145">Пользовательская конечная точка защищенных метаданных</span><span class="sxs-lookup"><span data-stu-id="a46d9-145">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="a46d9-146">Метаданные</span><span class="sxs-lookup"><span data-stu-id="a46d9-146">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="a46d9-147">Привязки</span><span class="sxs-lookup"><span data-stu-id="a46d9-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a46d9-148">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="a46d9-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a46d9-149">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="a46d9-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a46d9-150">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="a46d9-150">\<binding></span></span>](../../../misc/binding.md)
