---
title: '&lt;wsDualHttpBinding&gt;'
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
- wsDualHttpBinding Element
ms.assetid: fd8ac4e2-5641-473b-9115-73f14ab1c065
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a49b534ba22f4ac422eb26885388e24594b49afd
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2018
---
# <a name="ltwsdualhttpbindinggt"></a><span data-ttu-id="bcaa0-102">&lt;wsDualHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="bcaa0-102">&lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="bcaa0-103">Определяет безопасную, надежную привязку с возможностью взаимодействия, которая подходит для дуплексных контрактов службы или связи посредством посредников протокола SOAP.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-103">Defines a secure, reliable and interoperable binding that is suitable for duplex service contracts or communication through SOAP intermediaries.</span></span>  
  
 <span data-ttu-id="bcaa0-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bcaa0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bcaa0-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="bcaa0-105">\<bindings></span></span>  
<span data-ttu-id="bcaa0-106">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="bcaa0-106">\<wsDualHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcaa0-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bcaa0-107">Syntax</span></span>  
  
```xml  
<wsDualHttpBinding>  
        <binding name="string"  
        closeTimeout="TimeSpan"  
        openTimeout="TimeSpan"   
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
        bypassProxyOnLocal="Boolean"  
        clientBaseAddress="URI"  
        transactionFlow="Boolean"   
        hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxReceivedMessageSize="Integer"  
        messageEncoding="Text/Mtom"   
        proxyAddress="URI"  
  
textEncoding="Unicode/BigEndianUnicode/UTF8"  
        useDefaultWebProxy="Boolean">  
        <reliableSession ordered="Boolean"  
            inactivityTimeout="TimeSpan" />  
        <security mode="None/Message">  
           <message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"  
                negotiateServiceCredential="Boolean"  
                    algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />  
                </security>  
       <readerQuotas             maxArrayLength="Integer"            maxBytesPerRead="Integer"            maxDepth="Integer"             maxNameTableCharCount="Integer"                     maxStringContentLength="Integer" />    </binding>  
</wsDualHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bcaa0-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bcaa0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bcaa0-109">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bcaa0-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bcaa0-110">Attributes</span></span>  
  
|<span data-ttu-id="bcaa0-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bcaa0-111">Attribute</span></span>|<span data-ttu-id="bcaa0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bcaa0-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bcaa0-113">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="bcaa0-113">bypassProxyOnLocal</span></span>|<span data-ttu-id="bcaa0-114">Логическое значение, определяющее, будет ли выполняться обход прокси-сервера для локальных адресов.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-114">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="bcaa0-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-115">The default is `false`.</span></span>|  
|<span data-ttu-id="bcaa0-116">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="bcaa0-116">clientBaseAddress</span></span>|<span data-ttu-id="bcaa0-117">Универсальный код ресурса (URI), задающий базовый адрес, который клиент прослушивает для получения сообщений ответа от службы.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-117">A URI that sets the base address that the client listens to for response messages from the service.</span></span> <span data-ttu-id="bcaa0-118">Если значение задано, для прослушивания используется этот адрес (плюс per-channelGUID).</span><span class="sxs-lookup"><span data-stu-id="bcaa0-118">If specified, this address (plus a per-channelGUID) is used for listening.</span></span> <span data-ttu-id="bcaa0-119">Если значение не задано, базовый адрес клиента создается в соответствии с транспортом.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-119">If the value is not specified, the client base address is generated in a transport-specific manner.</span></span> <span data-ttu-id="bcaa0-120">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-120">The default is `null`.</span></span>|  
|<span data-ttu-id="bcaa0-121">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="bcaa0-121">closeTimeout</span></span>|<span data-ttu-id="bcaa0-122">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="bcaa0-123">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="bcaa0-124">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-124">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="bcaa0-125">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="bcaa0-125">hostnameComparisonMode</span></span>|<span data-ttu-id="bcaa0-126">Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="bcaa0-126">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="bcaa0-127">Это атрибут типа <xref:System.ServiceModel.HostNameComparisonMode>, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="bcaa0-127">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="bcaa0-128">Значение по умолчанию — <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, при котором имя узла в найденном соответствии не используется.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-128">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="bcaa0-129">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="bcaa0-129">maxBufferPoolSize</span></span>|<span data-ttu-id="bcaa0-130">Целое число, задающее максимальный размер буферного пула для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-130">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="bcaa0-131">Значение по умолчанию - 524 288 байт (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="bcaa0-131">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="bcaa0-132">Многие элементы Windows Communication Foundation (WCF) используют буферы.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-132">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="bcaa0-133">При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-133">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="bcaa0-134">Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-134">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="bcaa0-135">Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-135">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="bcaa0-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="bcaa0-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="bcaa0-137">Положительное целое число, задающее, в байтах, максимальный размер сообщения (включая заголовки), которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-137">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="bcaa0-138">Отправитель сообщения, превышающего это ограничение, получит ошибку SOAP.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-138">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="bcaa0-139">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-139">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="bcaa0-140">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-140">The default is 65536.</span></span>|  
|<span data-ttu-id="bcaa0-141">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="bcaa0-141">messageEncoding</span></span>|<span data-ttu-id="bcaa0-142">Определяет кодировщик, используемый для кодировки сообщения.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-142">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="bcaa0-143">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="bcaa0-143">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="bcaa0-144">-Text: Используется кодировщик текстовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-144">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="bcaa0-145">-Mtom: Используется кодировщик передачи сообщений организации 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="bcaa0-145">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="bcaa0-146">-Значение по умолчанию — текст.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-146">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="bcaa0-147">Это атрибут типа <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-147">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="bcaa0-148">имя</span><span class="sxs-lookup"><span data-stu-id="bcaa0-148">name</span></span>|<span data-ttu-id="bcaa0-149">Строка, содержащая имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-149">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="bcaa0-150">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-150">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="bcaa0-151">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-151">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="bcaa0-152">Дополнительные сведения о конфигурации по умолчанию и безымянные привязок и поведений см. в разделе [упрощенной конфигурации](../../../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="bcaa0-152">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="bcaa0-153">openTimeout</span><span class="sxs-lookup"><span data-stu-id="bcaa0-153">openTimeout</span></span>|<span data-ttu-id="bcaa0-154">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-154">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="bcaa0-155">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-155">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="bcaa0-156">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-156">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="bcaa0-157">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="bcaa0-157">proxyAddress</span></span>|<span data-ttu-id="bcaa0-158">Универсальный код ресурса (URI), задающий адрес прокси-сервера HTTP.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-158">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="bcaa0-159">Если параметр `useDefaultWebProxy` имеет значение `true`, данный параметр должен иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-159">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="bcaa0-160">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-160">The default is `null`.</span></span>|  
|<span data-ttu-id="bcaa0-161">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="bcaa0-161">receiveTimeout</span></span>|<span data-ttu-id="bcaa0-162">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-162">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="bcaa0-163">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-163">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="bcaa0-164">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-164">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="bcaa0-165">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="bcaa0-165">sendTimeout</span></span>|<span data-ttu-id="bcaa0-166">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-166">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="bcaa0-167">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-167">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="bcaa0-168">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-168">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="bcaa0-169">textEncoding</span><span class="sxs-lookup"><span data-stu-id="bcaa0-169">textEncoding</span></span>|<span data-ttu-id="bcaa0-170">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-170">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="bcaa0-171">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="bcaa0-171">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="bcaa0-172">-BigEndianUnicode: Юникод BigEndian.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-172">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="bcaa0-173">-Unicode: 16-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-173">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="bcaa0-174">-UTF8: 8-разрядная кодировка</span><span class="sxs-lookup"><span data-stu-id="bcaa0-174">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="bcaa0-175">Значение по умолчанию - UTF8.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-175">The default is UTF8.</span></span> <span data-ttu-id="bcaa0-176">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-176">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="bcaa0-177">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="bcaa0-177">transactionFlow</span></span>|<span data-ttu-id="bcaa0-178">Логическое значение, определяющее, поддерживает ли привязка потоковые спецификации WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-178">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="bcaa0-179">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-179">The default is `false`.</span></span>|  
|<span data-ttu-id="bcaa0-180">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="bcaa0-180">useDefaultWebProxy</span></span>|<span data-ttu-id="bcaa0-181">Логическое значение, указывающее, должен ли использоваться автоматически настроенный системный прокси-сервер HTTP.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-181">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="bcaa0-182">Если данный атрибут имеет значение `null`, прокси-адрес должен быть равен `true` (то есть не задан).</span><span class="sxs-lookup"><span data-stu-id="bcaa0-182">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="bcaa0-183">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-183">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bcaa0-184">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bcaa0-184">Child Elements</span></span>  
  
|<span data-ttu-id="bcaa0-185">Элемент</span><span class="sxs-lookup"><span data-stu-id="bcaa0-185">Element</span></span>|<span data-ttu-id="bcaa0-186">Описание</span><span class="sxs-lookup"><span data-stu-id="bcaa0-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bcaa0-187">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="bcaa0-187">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsdualhttpbinding.md)|<span data-ttu-id="bcaa0-188">Определяет параметры безопасности привязки.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-188">Defines the security settings for the binding.</span></span> <span data-ttu-id="bcaa0-189">Это элемент типа <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-189">This element is of type <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement>.</span></span>|  
|[<span data-ttu-id="bcaa0-190">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="bcaa0-190">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="bcaa0-191">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-191">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="bcaa0-192">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-192">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="bcaa0-193">reliableSession</span><span class="sxs-lookup"><span data-stu-id="bcaa0-193">reliableSession</span></span>](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|<span data-ttu-id="bcaa0-194">Указывает, устанавливаются ли между конечными точками канала надежные сеансы.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-194">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bcaa0-195">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bcaa0-195">Parent Elements</span></span>  
  
|<span data-ttu-id="bcaa0-196">Элемент</span><span class="sxs-lookup"><span data-stu-id="bcaa0-196">Element</span></span>|<span data-ttu-id="bcaa0-197">Описание</span><span class="sxs-lookup"><span data-stu-id="bcaa0-197">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bcaa0-198">\<bindings></span><span class="sxs-lookup"><span data-stu-id="bcaa0-198">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="bcaa0-199">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-199">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcaa0-200">Примечания</span><span class="sxs-lookup"><span data-stu-id="bcaa0-200">Remarks</span></span>  
 <span data-ttu-id="bcaa0-201">Объект `WSDualHttpBinding` предоставляет такую же поддержку протоколам веб-служб, как и объект `WSHttpBinding`, но применяется для дуплексных контрактов.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-201">The `WSDualHttpBinding` provides the same support for Web Service protocols as the `WSHttpBinding`, but for use with duplex contracts.</span></span> <span data-ttu-id="bcaa0-202">`WSDualHttpBinding` поддерживает только безопасность SOAP и требует надежного обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-202">`WSDualHttpBinding` only supports SOAP security and requires reliable messaging.</span></span> <span data-ttu-id="bcaa0-203">Для этой привязки необходимо, чтобы клиент имел открытый универсальный код ресурса (URI), предоставляющий конечную точку обратного вызова для службы.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-203">This binding requires that the client has a public URI that provides a callback endpoint for the service.</span></span> <span data-ttu-id="bcaa0-204">Это обеспечивается атрибутом `clientBaseAddress`.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-204">This is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="bcaa0-205">Двойная привязка предоставляет службе IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-205">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="bcaa0-206">Клиенту следует использовать механизм безопасности, чтобы гарантировать, что подключение выполняется только к доверенным службам.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-206">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
 <span data-ttu-id="bcaa0-207">Эту привязку можно использовать для надежной связи посредством одного или нескольких посредников протокола SOAP.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-207">This binding can be used to communicate reliably through one or more SOAP intermediaries.</span></span>  
  
 <span data-ttu-id="bcaa0-208">По умолчанию эта привязка создает стек времени выполнения с WS-ReliableMessaging для надежности, WS-Security для безопасности и проверки подлинности сообщений, HTTP для доставки сообщений и кодировкой сообщений Text/XML.</span><span class="sxs-lookup"><span data-stu-id="bcaa0-208">By default, this binding generates a runtime stack with WS-ReliableMessaging for reliability, WS-Security for message security and authentication, HTTP for message delivery, and a Text/XML message encoding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcaa0-209">Пример</span><span class="sxs-lookup"><span data-stu-id="bcaa0-209">Example</span></span>  
  
```xml  
<configuration>  
<system.ServiceModel>  
<bindings>  
<wsDualHttpBinding>  
    <binding   
        closeTimeout="00:00:10"  
        openTimeout="00:00:20"   
        receiveTimeout="00:00:30"  
        sendTimeout="00:00:40"  
        bypassProxyOnLocal="false"   
        clientBaseAddress="http://localhost:8001/client/"  
        transactionFlow="true"   
        hostNameComparisonMode="WeakWildcard"  
        maxReceivedMessageSize="1000"  
        messageEncoding="Mtom"   
        proxyAddress="http://foo/bar"   
        textEncoding="utf-16"  
        useDefaultWebProxy="false">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00" />  
        <security mode="None">  
            <message clientCredentialType="None"  
                negotiateServiceCredential="false"  
                algorithmSuite="Aes128" />  
        </security>  
    </binding>  
</wsDualHttpBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bcaa0-210">См. также</span><span class="sxs-lookup"><span data-stu-id="bcaa0-210">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpBinding>  
 <xref:System.ServiceModel.Configuration.WSDualHttpBindingElement>  
 [<span data-ttu-id="bcaa0-211">Привязки</span><span class="sxs-lookup"><span data-stu-id="bcaa0-211">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="bcaa0-212">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="bcaa0-212">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="bcaa0-213">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="bcaa0-213">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="bcaa0-214">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="bcaa0-214">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
