---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 924d68dd828622b74c5e424a695f80874391b453
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430341"
---
# <a name="mexhttpsbinding"></a><span data-ttu-id="f7c04-101">\<Мексхттпсбиндинг ></span><span class="sxs-lookup"><span data-stu-id="f7c04-101">\<mexHttpsBinding></span></span>
<span data-ttu-id="f7c04-102">Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) посредством HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f7c04-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
<span data-ttu-id="f7c04-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f7c04-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f7c04-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f7c04-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f7c04-105">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="f7c04-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="f7c04-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<мексхттпсбиндинг >**</span><span class="sxs-lookup"><span data-stu-id="f7c04-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpsBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7c04-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7c04-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7c04-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f7c04-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f7c04-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f7c04-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7c04-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f7c04-110">Attributes</span></span>  
  
|<span data-ttu-id="f7c04-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f7c04-111">Attribute</span></span>|<span data-ttu-id="f7c04-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f7c04-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="f7c04-113">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="f7c04-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="f7c04-114">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f7c04-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f7c04-115">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="f7c04-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="f7c04-116">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="f7c04-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="f7c04-117">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="f7c04-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="f7c04-118">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="f7c04-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="f7c04-119">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="f7c04-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="f7c04-120">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="f7c04-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="f7c04-121">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f7c04-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f7c04-122">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="f7c04-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="f7c04-123">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="f7c04-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="f7c04-124">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f7c04-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f7c04-125">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="f7c04-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="f7c04-126">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="f7c04-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="f7c04-127">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f7c04-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f7c04-128">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="f7c04-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7c04-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f7c04-129">Child Elements</span></span>  
 <span data-ttu-id="f7c04-130">Нет.</span><span class="sxs-lookup"><span data-stu-id="f7c04-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7c04-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f7c04-131">Parent Elements</span></span>  
  
|<span data-ttu-id="f7c04-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="f7c04-132">Element</span></span>|<span data-ttu-id="f7c04-133">Описание</span><span class="sxs-lookup"><span data-stu-id="f7c04-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7c04-134">привязки \<></span><span class="sxs-lookup"><span data-stu-id="f7c04-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="f7c04-135">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="f7c04-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7c04-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="f7c04-136">Remarks</span></span>  
 <span data-ttu-id="f7c04-137">Эта привязка по существу является привязкой `WSHttpBinding`, которая поддерживает безопасность уровня транспорта с помощью сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f7c04-137">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="f7c04-138">Дополнительные сведения о настройке и использовании такой конечной точки метаданных см. в разделе [как настроить настраиваемую привязку WS-Metadata Exchange](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [как получать метаданные через привязку обмена метаданными](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), а также образец [настраиваемой конечной точки безопасных метаданных](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="f7c04-138">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c04-139">См. также</span><span class="sxs-lookup"><span data-stu-id="f7c04-139">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="f7c04-140">Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="f7c04-140">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="f7c04-141">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="f7c04-141">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="f7c04-142">Практическое руководство. Настройка пользовательской привязки WS-Metadata Exchange</span><span class="sxs-lookup"><span data-stu-id="f7c04-142">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="f7c04-143">Практическое руководство. Получение метаданных через привязку, не использующую MEX</span><span class="sxs-lookup"><span data-stu-id="f7c04-143">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="f7c04-144">Пользовательская конечная точка защищенных метаданных</span><span class="sxs-lookup"><span data-stu-id="f7c04-144">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="f7c04-145">Метаданные</span><span class="sxs-lookup"><span data-stu-id="f7c04-145">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="f7c04-146">Привязки</span><span class="sxs-lookup"><span data-stu-id="f7c04-146">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f7c04-147">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="f7c04-147">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f7c04-148">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f7c04-148">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f7c04-149">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="f7c04-149">\<binding></span></span>](bindings.md)
