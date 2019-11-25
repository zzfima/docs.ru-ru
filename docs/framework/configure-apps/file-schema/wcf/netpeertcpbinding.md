---
title: <netPeerTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
ms.openlocfilehash: 921da4d0b010672585a045d58d03182e480a255a
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140727"
---
# <a name="netpeertcpbinding"></a><span data-ttu-id="3b3e1-101">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="3b3e1-101">\<netPeerTcpBinding></span></span>
<span data-ttu-id="3b3e1-102">Определяет привязку для обмена TCP-сообщениями через одноранговый канал.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-102">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
<span data-ttu-id="3b3e1-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3b3e1-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3b3e1-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3b3e1-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3b3e1-105">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="3b3e1-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="3b3e1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<netPeerTcpBinding >**</span><span class="sxs-lookup"><span data-stu-id="3b3e1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netPeerTcpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b3e1-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b3e1-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b3e1-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3b3e1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3b3e1-109">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b3e1-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3b3e1-110">Attributes</span></span>  
  
|<span data-ttu-id="3b3e1-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3b3e1-111">Attribute</span></span>|<span data-ttu-id="3b3e1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3b3e1-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3b3e1-113">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="3b3e1-113">closeTimeout</span></span>|<span data-ttu-id="3b3e1-114">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="3b3e1-115">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3b3e1-116">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-116">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="3b3e1-117">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="3b3e1-117">listenIPAddress</span></span>|<span data-ttu-id="3b3e1-118">Строка, указывающая IP-адрес, на котором одноранговый узел будет ожидать TCP-сообщения.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-118">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="3b3e1-119">Значение по умолчанию: `null`.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-119">The default is `null`.</span></span>|  
|<span data-ttu-id="3b3e1-120">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="3b3e1-120">maxBufferPoolSize</span></span>|<span data-ttu-id="3b3e1-121">Целое число, задающее максимальный размер буферного пула для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-121">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="3b3e1-122">Значение по умолчанию - 524 288 байт (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="3b3e1-122">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="3b3e1-123">Многие элементы Windows Communication Foundation (WCF) используют буферы.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-123">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="3b3e1-124">При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-124">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="3b3e1-125">Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-125">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="3b3e1-126">Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-126">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="3b3e1-127">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="3b3e1-127">maxReceivedMessageSize</span></span>|<span data-ttu-id="3b3e1-128">Положительное целое число, задающее, в байтах, максимальный размер сообщения (включая заголовки), которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-128">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="3b3e1-129">Отправитель сообщения, превышающего это ограничение, получит ошибку SOAP.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-129">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="3b3e1-130">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-130">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="3b3e1-131">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-131">The default is 65536.</span></span>|  
|<span data-ttu-id="3b3e1-132">имя</span><span class="sxs-lookup"><span data-stu-id="3b3e1-132">name</span></span>|<span data-ttu-id="3b3e1-133">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-133">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="3b3e1-134">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-134">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="3b3e1-135">Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-135">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="3b3e1-136">Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="3b3e1-136">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="3b3e1-137">openTimeout</span><span class="sxs-lookup"><span data-stu-id="3b3e1-137">openTimeout</span></span>|<span data-ttu-id="3b3e1-138">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-138">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="3b3e1-139">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-139">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3b3e1-140">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-140">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="3b3e1-141">порт</span><span class="sxs-lookup"><span data-stu-id="3b3e1-141">port</span></span>|<span data-ttu-id="3b3e1-142">Целое число, задающее порт сетевого интерфейса, на котором эта привязка будет обрабатывать TCP-сообщения однорангового канала.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-142">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="3b3e1-143">Это значение должно принадлежать диапазону от <xref:System.Net.IPEndPoint.MinPort> до <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-143">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="3b3e1-144">Значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-144">The default is 0.</span></span>|  
|<span data-ttu-id="3b3e1-145">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="3b3e1-145">receiveTimeout</span></span>|<span data-ttu-id="3b3e1-146">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-146">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="3b3e1-147">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-147">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3b3e1-148">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-148">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="3b3e1-149">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="3b3e1-149">sendTimeout</span></span>|<span data-ttu-id="3b3e1-150">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-150">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="3b3e1-151">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-151">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="3b3e1-152">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-152">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3b3e1-153">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3b3e1-153">Child Elements</span></span>  
  
|<span data-ttu-id="3b3e1-154">Элемент</span><span class="sxs-lookup"><span data-stu-id="3b3e1-154">Element</span></span>|<span data-ttu-id="3b3e1-155">Описание</span><span class="sxs-lookup"><span data-stu-id="3b3e1-155">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3b3e1-156">[\<Реадеркуотас >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3b3e1-156">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="3b3e1-157">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-157">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="3b3e1-158">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-158">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="3b3e1-159">сопоставитель \<</span><span class="sxs-lookup"><span data-stu-id="3b3e1-159">\<resolver></span></span>](resolver.md)|<span data-ttu-id="3b3e1-160">Указывает распознаватель одноранговых узлов, используемый данной привязкой для разрешения идентификаторов сетки одноранговых узлов в IP-адреса конечных точек узлов этой сетки.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-160">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[<span data-ttu-id="3b3e1-161">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="3b3e1-161">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="3b3e1-162">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-162">Defines the security settings for the message.</span></span> <span data-ttu-id="3b3e1-163">Это элемент типа <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-163">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3b3e1-164">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3b3e1-164">Parent Elements</span></span>  
  
|<span data-ttu-id="3b3e1-165">Элемент</span><span class="sxs-lookup"><span data-stu-id="3b3e1-165">Element</span></span>|<span data-ttu-id="3b3e1-166">Описание</span><span class="sxs-lookup"><span data-stu-id="3b3e1-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b3e1-167">привязки\<</span><span class="sxs-lookup"><span data-stu-id="3b3e1-167">\<bindings></span></span>](bindings.md)|<span data-ttu-id="3b3e1-168">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-168">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b3e1-169">Заметки</span><span class="sxs-lookup"><span data-stu-id="3b3e1-169">Remarks</span></span>  
 <span data-ttu-id="3b3e1-170">Эта привязка обеспечивает поддержку для создания одноранговых и многопользовательских приложений, использующих передачу данных по протоколу TCP.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-170">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="3b3e1-171">Каждый одноранговый узел может содержать несколько одноранговых каналов, определенных этим типом привязки.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-171">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b3e1-172">Пример</span><span class="sxs-lookup"><span data-stu-id="3b3e1-172">Example</span></span>  
 <span data-ttu-id="3b3e1-173">Следующий пример демонстрирует применение привязки NetPeerTcpBinding, обеспечивающей многопользовательскую связь с использованием однорангового канала.</span><span class="sxs-lookup"><span data-stu-id="3b3e1-173">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="3b3e1-174">Подробный сценарий использования этой привязки см. в разделе [net peer TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="3b3e1-174">For a detailed scenario of using this binding, see [Net Peer TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3b3e1-175">См. также</span><span class="sxs-lookup"><span data-stu-id="3b3e1-175">See also</span></span>

- <xref:System.ServiceModel.NetPeerTcpBinding>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>
- [<span data-ttu-id="3b3e1-176">Привязки</span><span class="sxs-lookup"><span data-stu-id="3b3e1-176">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3b3e1-177">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="3b3e1-177">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3b3e1-178">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="3b3e1-178">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="3b3e1-179">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="3b3e1-179">\<binding></span></span>](bindings.md)
- <span data-ttu-id="3b3e1-180">[Сетевой одноранговый TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="3b3e1-180">[Net Peer TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span></span>
- [<span data-ttu-id="3b3e1-181">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="3b3e1-181">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
