---
title: '&lt;netPeerTcpBinding&gt;'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a890243ee12202efa9743a6151255525c7f78be2
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2018
---
# <a name="ltnetpeertcpbindinggt"></a><span data-ttu-id="b1630-102">&lt;netPeerTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="b1630-102">&lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="b1630-103">Определяет привязку для обмена TCP-сообщениями через одноранговый канал.</span><span class="sxs-lookup"><span data-stu-id="b1630-103">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
 <span data-ttu-id="b1630-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b1630-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b1630-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="b1630-105">\<bindings></span></span>  
<span data-ttu-id="b1630-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="b1630-106">\<netPeerTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1630-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1630-107">Syntax</span></span>  
  
```xml  
<netPeerBinding>  
    <binding name="string"  
         closeTimeout="TimeSpan"  
         openTimeout="TimeSpan"   
         receiveTimeout="TimeSpan"  
         sendTimeout="TimeSpan"  
         listenIPAddress="String"  
          maxBufferPoolSize="integer"  
         maxReceiveMessageSize="Integer"   
         port="Integer"  
         <security mode="None/Transport/Message/TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1630-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b1630-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b1630-109">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b1630-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1630-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b1630-110">Attributes</span></span>  
  
|<span data-ttu-id="b1630-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b1630-111">Attribute</span></span>|<span data-ttu-id="b1630-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b1630-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b1630-113">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="b1630-113">closeTimeout</span></span>|<span data-ttu-id="b1630-114">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="b1630-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="b1630-115">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="b1630-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b1630-116">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="b1630-116">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="b1630-117">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="b1630-117">listenIPAddress</span></span>|<span data-ttu-id="b1630-118">Строка, указывающая IP-адрес, на котором одноранговый узел будет ожидать TCP-сообщения.</span><span class="sxs-lookup"><span data-stu-id="b1630-118">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="b1630-119">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="b1630-119">The default is `null`.</span></span>|  
|<span data-ttu-id="b1630-120">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="b1630-120">maxBufferPoolSize</span></span>|<span data-ttu-id="b1630-121">Целое число, задающее максимальный размер буферного пула для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="b1630-121">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="b1630-122">Значение по умолчанию - 524 288 байт (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="b1630-122">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="b1630-123">Многие элементы Windows Communication Foundation (WCF) используют буферы.</span><span class="sxs-lookup"><span data-stu-id="b1630-123">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="b1630-124">При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b1630-124">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="b1630-125">Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="b1630-125">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="b1630-126">Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.</span><span class="sxs-lookup"><span data-stu-id="b1630-126">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="b1630-127">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="b1630-127">maxReceivedMessageSize</span></span>|<span data-ttu-id="b1630-128">Положительное целое число, задающее, в байтах, максимальный размер сообщения (включая заголовки), которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="b1630-128">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="b1630-129">Отправитель сообщения, превышающего это ограничение, получит ошибку SOAP.</span><span class="sxs-lookup"><span data-stu-id="b1630-129">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="b1630-130">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="b1630-130">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="b1630-131">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="b1630-131">The default is 65536.</span></span>|  
|<span data-ttu-id="b1630-132">имя</span><span class="sxs-lookup"><span data-stu-id="b1630-132">name</span></span>|<span data-ttu-id="b1630-133">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="b1630-133">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="b1630-134">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="b1630-134">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="b1630-135">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="b1630-135">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="b1630-136">Дополнительные сведения о конфигурации по умолчанию и безымянные привязок и поведений см. в разделе [упрощенной конфигурации](../../../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="b1630-136">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="b1630-137">openTimeout</span><span class="sxs-lookup"><span data-stu-id="b1630-137">openTimeout</span></span>|<span data-ttu-id="b1630-138">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="b1630-138">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="b1630-139">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="b1630-139">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b1630-140">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="b1630-140">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="b1630-141">порт</span><span class="sxs-lookup"><span data-stu-id="b1630-141">port</span></span>|<span data-ttu-id="b1630-142">Целое число, задающее порт сетевого интерфейса, на котором эта привязка будет обрабатывать TCP-сообщения однорангового канала.</span><span class="sxs-lookup"><span data-stu-id="b1630-142">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="b1630-143">Это значение должно принадлежать диапазону от <xref:System.Net.IPEndPoint.MinPort> до <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="b1630-143">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="b1630-144">Значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="b1630-144">The default is 0.</span></span>|  
|<span data-ttu-id="b1630-145">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="b1630-145">receiveTimeout</span></span>|<span data-ttu-id="b1630-146">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="b1630-146">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="b1630-147">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="b1630-147">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b1630-148">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="b1630-148">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="b1630-149">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="b1630-149">sendTimeout</span></span>|<span data-ttu-id="b1630-150">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="b1630-150">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="b1630-151">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="b1630-151">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b1630-152">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="b1630-152">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b1630-153">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b1630-153">Child Elements</span></span>  
  
|<span data-ttu-id="b1630-154">Элемент</span><span class="sxs-lookup"><span data-stu-id="b1630-154">Element</span></span>|<span data-ttu-id="b1630-155">Описание</span><span class="sxs-lookup"><span data-stu-id="b1630-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1630-156">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="b1630-156">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="b1630-157">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="b1630-157">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="b1630-158">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="b1630-158">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="b1630-159">\<resolver></span><span class="sxs-lookup"><span data-stu-id="b1630-159">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="b1630-160">Указывает распознаватель одноранговых узлов, используемый данной привязкой для разрешения идентификаторов сетки одноранговых узлов в IP-адреса конечных точек узлов этой сетки.</span><span class="sxs-lookup"><span data-stu-id="b1630-160">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[<span data-ttu-id="b1630-161">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="b1630-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="b1630-162">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="b1630-162">Defines the security settings for the message.</span></span> <span data-ttu-id="b1630-163">Это элемент типа <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="b1630-163">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b1630-164">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b1630-164">Parent Elements</span></span>  
  
|<span data-ttu-id="b1630-165">Элемент</span><span class="sxs-lookup"><span data-stu-id="b1630-165">Element</span></span>|<span data-ttu-id="b1630-166">Описание</span><span class="sxs-lookup"><span data-stu-id="b1630-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1630-167">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b1630-167">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="b1630-168">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="b1630-168">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1630-169">Примечания</span><span class="sxs-lookup"><span data-stu-id="b1630-169">Remarks</span></span>  
 <span data-ttu-id="b1630-170">Эта привязка обеспечивает поддержку для создания одноранговых и многопользовательских приложений, использующих передачу данных по протоколу TCP.</span><span class="sxs-lookup"><span data-stu-id="b1630-170">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="b1630-171">Каждый одноранговый узел может содержать несколько одноранговых каналов, определенных этим типом привязки.</span><span class="sxs-lookup"><span data-stu-id="b1630-171">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1630-172">Пример</span><span class="sxs-lookup"><span data-stu-id="b1630-172">Example</span></span>  
 <span data-ttu-id="b1630-173">Следующий пример демонстрирует применение привязки NetPeerTcpBinding, обеспечивающей многопользовательскую связь с использованием однорангового канала.</span><span class="sxs-lookup"><span data-stu-id="b1630-173">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="b1630-174">Подробные сценарий с помощью этой привязки в разделе [Net TCP одноранговых](http://msdn.microsoft.com/library/31f4db66-edb2-40a6-b92a-14098e92acae).</span><span class="sxs-lookup"><span data-stu-id="b1630-174">For a detailed scenario of using this binding, see [Net Peer TCP](http://msdn.microsoft.com/library/31f4db66-edb2-40a6-b92a-14098e92acae).</span></span>  
  
```xml  
<configuration>  
<system.ServiceModel>  
<bindings>  
<netPeerBinding>  
    <binding   
         closeTimeout="00:00:10"  
         openTimeout="00:00:20"   
         receiveTimeout="00:00:30"  
         sendTimeout="00:00:40"  
         maxBufferSize="1001"  
         maxConnections="123"   
         maxReceiveMessageSize="1000">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00"  
            enabled="true" />  
        <security mode="TransportWithMessageCredential">  
            <message clientCredentialType="CardSpace" />  
        </security>  
    </binding>  
</netPeerBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1630-175">См. также</span><span class="sxs-lookup"><span data-stu-id="b1630-175">See Also</span></span>  
 <xref:System.ServiceModel.NetPeerTcpBinding>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>  
 [<span data-ttu-id="b1630-176">Привязки</span><span class="sxs-lookup"><span data-stu-id="b1630-176">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="b1630-177">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="b1630-177">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="b1630-178">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="b1630-178">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="b1630-179">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="b1630-179">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="b1630-180">NET одноранговых TCP</span><span class="sxs-lookup"><span data-stu-id="b1630-180">Net Peer TCP</span></span>](http://msdn.microsoft.com/library/31f4db66-edb2-40a6-b92a-14098e92acae)  
 [<span data-ttu-id="b1630-181">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="b1630-181">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
