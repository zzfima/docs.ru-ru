---
title: <netPeerTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
ms.openlocfilehash: a039e805bc4378582d7a7bcf6ef84591ec3d2b6b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261442"
---
# <a name="netpeertcpbinding"></a><span data-ttu-id="ba63a-101">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="ba63a-101">\<netPeerTcpBinding></span></span>
<span data-ttu-id="ba63a-102">Определяет привязку для обмена TCP-сообщениями через одноранговый канал.</span><span class="sxs-lookup"><span data-stu-id="ba63a-102">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
 <span data-ttu-id="ba63a-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ba63a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ba63a-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="ba63a-104">\<bindings></span></span>  
<span data-ttu-id="ba63a-105">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="ba63a-105">\<netPeerTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba63a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba63a-106">Syntax</span></span>  
  
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
           port="Integer">
    <security mode="None/Transport/Message/TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba63a-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ba63a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ba63a-108">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ba63a-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba63a-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ba63a-109">Attributes</span></span>  
  
|<span data-ttu-id="ba63a-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ba63a-110">Attribute</span></span>|<span data-ttu-id="ba63a-111">Описание</span><span class="sxs-lookup"><span data-stu-id="ba63a-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ba63a-112">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="ba63a-112">closeTimeout</span></span>|<span data-ttu-id="ba63a-113">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="ba63a-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="ba63a-114">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ba63a-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ba63a-115">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ba63a-115">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="ba63a-116">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="ba63a-116">listenIPAddress</span></span>|<span data-ttu-id="ba63a-117">Строка, указывающая IP-адрес, на котором одноранговый узел будет ожидать TCP-сообщения.</span><span class="sxs-lookup"><span data-stu-id="ba63a-117">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="ba63a-118">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="ba63a-118">The default is `null`.</span></span>|  
|<span data-ttu-id="ba63a-119">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="ba63a-119">maxBufferPoolSize</span></span>|<span data-ttu-id="ba63a-120">Целое число, задающее максимальный размер буферного пула для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="ba63a-120">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="ba63a-121">Значение по умолчанию - 524 288 байт (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="ba63a-121">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="ba63a-122">Многие элементы Windows Communication Foundation (WCF) используют буферы.</span><span class="sxs-lookup"><span data-stu-id="ba63a-122">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="ba63a-123">При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ba63a-123">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="ba63a-124">Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="ba63a-124">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="ba63a-125">Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.</span><span class="sxs-lookup"><span data-stu-id="ba63a-125">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="ba63a-126">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="ba63a-126">maxReceivedMessageSize</span></span>|<span data-ttu-id="ba63a-127">Положительное целое число, задающее, в байтах, максимальный размер сообщения (включая заголовки), которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="ba63a-127">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="ba63a-128">Отправитель сообщения, превышающего это ограничение, получит ошибку SOAP.</span><span class="sxs-lookup"><span data-stu-id="ba63a-128">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="ba63a-129">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="ba63a-129">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="ba63a-130">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="ba63a-130">The default is 65536.</span></span>|  
|<span data-ttu-id="ba63a-131">имя</span><span class="sxs-lookup"><span data-stu-id="ba63a-131">name</span></span>|<span data-ttu-id="ba63a-132">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="ba63a-132">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="ba63a-133">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="ba63a-133">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="ba63a-134">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="ba63a-134">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="ba63a-135">Дополнительные сведения о конфигурации по умолчанию и безымянных привязках и поведениях см. в разделе [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="ba63a-135">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="ba63a-136">openTimeout</span><span class="sxs-lookup"><span data-stu-id="ba63a-136">openTimeout</span></span>|<span data-ttu-id="ba63a-137">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="ba63a-137">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="ba63a-138">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ba63a-138">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ba63a-139">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ba63a-139">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="ba63a-140">порт</span><span class="sxs-lookup"><span data-stu-id="ba63a-140">port</span></span>|<span data-ttu-id="ba63a-141">Целое число, задающее порт сетевого интерфейса, на котором эта привязка будет обрабатывать TCP-сообщения однорангового канала.</span><span class="sxs-lookup"><span data-stu-id="ba63a-141">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="ba63a-142">Это значение должно принадлежать диапазону от <xref:System.Net.IPEndPoint.MinPort> до <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="ba63a-142">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="ba63a-143">Значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="ba63a-143">The default is 0.</span></span>|  
|<span data-ttu-id="ba63a-144">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="ba63a-144">receiveTimeout</span></span>|<span data-ttu-id="ba63a-145">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="ba63a-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="ba63a-146">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ba63a-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ba63a-147">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="ba63a-147">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="ba63a-148">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="ba63a-148">sendTimeout</span></span>|<span data-ttu-id="ba63a-149">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="ba63a-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="ba63a-150">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="ba63a-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ba63a-151">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ba63a-151">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba63a-152">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ba63a-152">Child Elements</span></span>  
  
|<span data-ttu-id="ba63a-153">Элемент</span><span class="sxs-lookup"><span data-stu-id="ba63a-153">Element</span></span>|<span data-ttu-id="ba63a-154">Описание:</span><span class="sxs-lookup"><span data-stu-id="ba63a-154">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba63a-155">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="ba63a-155">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="ba63a-156">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="ba63a-156">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="ba63a-157">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="ba63a-157">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="ba63a-158">\<resolver></span><span class="sxs-lookup"><span data-stu-id="ba63a-158">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="ba63a-159">Указывает распознаватель одноранговых узлов, используемый данной привязкой для разрешения идентификаторов сетки одноранговых узлов в IP-адреса конечных точек узлов этой сетки.</span><span class="sxs-lookup"><span data-stu-id="ba63a-159">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[<span data-ttu-id="ba63a-160">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="ba63a-160">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="ba63a-161">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="ba63a-161">Defines the security settings for the message.</span></span> <span data-ttu-id="ba63a-162">Это элемент типа <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="ba63a-162">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba63a-163">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ba63a-163">Parent Elements</span></span>  
  
|<span data-ttu-id="ba63a-164">Элемент</span><span class="sxs-lookup"><span data-stu-id="ba63a-164">Element</span></span>|<span data-ttu-id="ba63a-165">Описание</span><span class="sxs-lookup"><span data-stu-id="ba63a-165">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba63a-166">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="ba63a-166">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="ba63a-167">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="ba63a-167">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba63a-168">Примечания</span><span class="sxs-lookup"><span data-stu-id="ba63a-168">Remarks</span></span>  
 <span data-ttu-id="ba63a-169">Эта привязка обеспечивает поддержку для создания одноранговых и многопользовательских приложений, использующих передачу данных по протоколу TCP.</span><span class="sxs-lookup"><span data-stu-id="ba63a-169">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="ba63a-170">Каждый одноранговый узел может содержать несколько одноранговых каналов, определенных этим типом привязки.</span><span class="sxs-lookup"><span data-stu-id="ba63a-170">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba63a-171">Пример</span><span class="sxs-lookup"><span data-stu-id="ba63a-171">Example</span></span>  
 <span data-ttu-id="ba63a-172">Следующий пример демонстрирует применение привязки NetPeerTcpBinding, обеспечивающей многопользовательскую связь с использованием однорангового канала.</span><span class="sxs-lookup"><span data-stu-id="ba63a-172">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="ba63a-173">Подробный сценарий применения этой привязки, см. в разделе [Net TCP одноранговых](https://msdn.microsoft.com/library/31f4db66-edb2-40a6-b92a-14098e92acae).</span><span class="sxs-lookup"><span data-stu-id="ba63a-173">For a detailed scenario of using this binding, see [Net Peer TCP](https://msdn.microsoft.com/library/31f4db66-edb2-40a6-b92a-14098e92acae).</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <netPeerBinding>
        <binding closeTimeout="00:00:10"
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
  
## <a name="see-also"></a><span data-ttu-id="ba63a-174">См. также</span><span class="sxs-lookup"><span data-stu-id="ba63a-174">See also</span></span>
- <xref:System.ServiceModel.NetPeerTcpBinding>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>
- [<span data-ttu-id="ba63a-175">Привязки</span><span class="sxs-lookup"><span data-stu-id="ba63a-175">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="ba63a-176">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="ba63a-176">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ba63a-177">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="ba63a-177">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ba63a-178">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ba63a-178">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="ba63a-179">Привязка NetPeerTcpBinding</span><span class="sxs-lookup"><span data-stu-id="ba63a-179">Net Peer TCP</span></span>](https://msdn.microsoft.com/library/31f4db66-edb2-40a6-b92a-14098e92acae)
- [<span data-ttu-id="ba63a-180">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="ba63a-180">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
