---
title: <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
ms.openlocfilehash: 26d0b6dbf950a32fabd5ac3c3aeb2546a0744863
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55280986"
---
# <a name="ws2007federationhttpbinding"></a><span data-ttu-id="dc94f-101">\<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="dc94f-101">\<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="dc94f-102">Надежная и совместимая привязка, производный от [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) и поддерживает федеративную безопасность.</span><span class="sxs-lookup"><span data-stu-id="dc94f-102">A secure and interoperable binding that derives from [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) and supports federated security.</span></span>  
  
 <span data-ttu-id="dc94f-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dc94f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="dc94f-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="dc94f-104">\<bindings></span></span>  
<span data-ttu-id="dc94f-105">\<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="dc94f-105">\<ws2007FederationHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc94f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc94f-106">Syntax</span></span>  
  
```xml  
<ws2007FederationHttpBinding>
  <binding bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxReceivedMessageSize="integer"
           messageEncoding="Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           privacyNoticeAt="Uri"
           privacyNoticeVersion="Integer"
           proxyAddress="Uri"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</ws2007FederationHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc94f-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dc94f-107">Attributes and Elements</span></span>  
 <span data-ttu-id="dc94f-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dc94f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc94f-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dc94f-109">Attributes</span></span>  
  
|<span data-ttu-id="dc94f-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dc94f-110">Attribute</span></span>|<span data-ttu-id="dc94f-111">Описание</span><span class="sxs-lookup"><span data-stu-id="dc94f-111">Description</span></span>|  
|---------------|-----------------|  
|`bypassProxyOnLocal`|<span data-ttu-id="dc94f-112">Значение, определяющее, будет ли выполняться обход прокси-сервера для локальных адресов.</span><span class="sxs-lookup"><span data-stu-id="dc94f-112">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="dc94f-113">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="dc94f-113">The default is `false`.</span></span>|  
|`closeTimeout`|<span data-ttu-id="dc94f-114">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="dc94f-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="dc94f-115">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="dc94f-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="dc94f-116">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="dc94f-116">The default is 00:01:00.</span></span>|  
|`hostnameComparisonMode`|<span data-ttu-id="dc94f-117">Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="dc94f-117">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="dc94f-118">Это атрибут типа <xref:System.ServiceModel.HostNameComparisonMode>, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="dc94f-118">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="dc94f-119">Значение по умолчанию — <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, при котором имя узла в найденном соответствии не используется.</span><span class="sxs-lookup"><span data-stu-id="dc94f-119">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="dc94f-120">Максимальный размер буферного пула для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="dc94f-120">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="dc94f-121">Значение по умолчанию - 524 288 байт (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="dc94f-121">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="dc94f-122">Многие элементы Windows Communication Foundation (WCF) используют буферы.</span><span class="sxs-lookup"><span data-stu-id="dc94f-122">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="dc94f-123">При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов.</span><span class="sxs-lookup"><span data-stu-id="dc94f-123">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="dc94f-124">Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="dc94f-124">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="dc94f-125">Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.</span><span class="sxs-lookup"><span data-stu-id="dc94f-125">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="dc94f-126">Максимальный размер сообщения (в байтах), включая заголовки, которое можно получить по каналу, настроенному с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="dc94f-126">The maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="dc94f-127">Отправитель сообщения, которое превысит это ограничение, получает ошибку SOAP.</span><span class="sxs-lookup"><span data-stu-id="dc94f-127">The sender of a message that exceeds this limit receives a SOAP fault.</span></span> <span data-ttu-id="dc94f-128">Получатель отклоняет сообщение и создает запись о событии в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="dc94f-128">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="dc94f-129">Значение по умолчанию — 65536.</span><span class="sxs-lookup"><span data-stu-id="dc94f-129">The default is 65536.</span></span>|  
|`messageEncoding`|<span data-ttu-id="dc94f-130">Определяет кодировщик, используемый для кодировки сообщения.</span><span class="sxs-lookup"><span data-stu-id="dc94f-130">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="dc94f-131">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="dc94f-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="dc94f-132">-Текст: Используйте кодировщик текстовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="dc94f-132">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="dc94f-133">-Mtom: Используется кодировщик передачи сообщений организации 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="dc94f-133">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="dc94f-134">Значение по умолчанию - Text.</span><span class="sxs-lookup"><span data-stu-id="dc94f-134">The default is Text.</span></span><br /><br /> <span data-ttu-id="dc94f-135">Это атрибут типа <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="dc94f-135">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="dc94f-136">Имя конфигурации привязки.</span><span class="sxs-lookup"><span data-stu-id="dc94f-136">The configuration name of the binding.</span></span> <span data-ttu-id="dc94f-137">Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.</span><span class="sxs-lookup"><span data-stu-id="dc94f-137">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="dc94f-138">Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.</span><span class="sxs-lookup"><span data-stu-id="dc94f-138">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="dc94f-139">Дополнительные сведения о конфигурации по умолчанию и безымянных привязках и поведениях см. в разделе [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="dc94f-139">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="dc94f-140">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="dc94f-140">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="dc94f-141">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="dc94f-141">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="dc94f-142">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="dc94f-142">The default is 00:01:00.</span></span>|  
|`privactyNoticeAt`|<span data-ttu-id="dc94f-143">Универсальный код ресурса (URI), определяющий расположение примечания о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="dc94f-143">A URI at which the privacy notice is located.</span></span>|  
|`privactyNoticeVersion`|<span data-ttu-id="dc94f-144">Версия текущего примечания о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="dc94f-144">The version of the current privacy notice.</span></span>|  
|`proxyAddress`|<span data-ttu-id="dc94f-145">Универсальный код ресурса (URI), задающий адрес прокси-сервера HTTP.</span><span class="sxs-lookup"><span data-stu-id="dc94f-145">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="dc94f-146">Если параметр `useDefaultWebProxy` имеет значение `true`, данный параметр должен иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="dc94f-146">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="dc94f-147">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="dc94f-147">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="dc94f-148">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="dc94f-148">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="dc94f-149">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="dc94f-149">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="dc94f-150">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="dc94f-150">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="dc94f-151">Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="dc94f-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="dc94f-152">Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="dc94f-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="dc94f-153">Значение по умолчанию - 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="dc94f-153">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="dc94f-154">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="dc94f-154">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="dc94f-155">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="dc94f-155">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="dc94f-156">-BigEndianUnicode: Обратный порядок байтов кодировка Юникод.</span><span class="sxs-lookup"><span data-stu-id="dc94f-156">-   BigEndianUnicode: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="dc94f-157">-Юникод. 16-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="dc94f-157">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="dc94f-158">-UTF8: 8-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="dc94f-158">-   UTF8: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="dc94f-159">Значение по умолчанию - UTF8.</span><span class="sxs-lookup"><span data-stu-id="dc94f-159">The default is UTF8.</span></span> <span data-ttu-id="dc94f-160">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="dc94f-160">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transactionFlow`|<span data-ttu-id="dc94f-161">Значение, определяющее, поддерживает ли привязка потоки WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="dc94f-161">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="dc94f-162">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="dc94f-162">The default is `false`.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="dc94f-163">Значение, указывающее, должен ли использоваться автоматически настроенный системный прокси-сервер HTTP.</span><span class="sxs-lookup"><span data-stu-id="dc94f-163">A value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="dc94f-164">Если данный атрибут имеет значение `null`, прокси-адрес должен быть равен `true` (то есть не задан).</span><span class="sxs-lookup"><span data-stu-id="dc94f-164">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="dc94f-165">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="dc94f-165">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc94f-166">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dc94f-166">Child Elements</span></span>  
  
|<span data-ttu-id="dc94f-167">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc94f-167">Element</span></span>|<span data-ttu-id="dc94f-168">Описание:</span><span class="sxs-lookup"><span data-stu-id="dc94f-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc94f-169">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="dc94f-169">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="dc94f-170">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="dc94f-170">Defines the security settings for the message.</span></span> <span data-ttu-id="dc94f-171">Это элемент типа <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="dc94f-171">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|  
|[<span data-ttu-id="dc94f-172">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="dc94f-172">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="dc94f-173">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="dc94f-173">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="dc94f-174">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="dc94f-174">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="dc94f-175">reliableSession</span><span class="sxs-lookup"><span data-stu-id="dc94f-175">reliableSession</span></span>](https://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|<span data-ttu-id="dc94f-176">Указывает, устанавливаются ли между конечными точками канала надежные сеансы.</span><span class="sxs-lookup"><span data-stu-id="dc94f-176">Specifies whether reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dc94f-177">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dc94f-177">Parent Elements</span></span>  
  
|<span data-ttu-id="dc94f-178">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc94f-178">Element</span></span>|<span data-ttu-id="dc94f-179">Описание:</span><span class="sxs-lookup"><span data-stu-id="dc94f-179">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc94f-180">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="dc94f-180">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="dc94f-181">Этот элемент содержит коллекцию стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="dc94f-181">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc94f-182">Примечания</span><span class="sxs-lookup"><span data-stu-id="dc94f-182">Remarks</span></span>  
 <span data-ttu-id="dc94f-183">Федерация - это возможность совместного использования удостоверений между несколькими предприятиями или доверенными доменами в целях проверки подлинности и авторизации.</span><span class="sxs-lookup"><span data-stu-id="dc94f-183">Federation is the ability to share identities across multiple enterprises or trust domains for authentication and authorization.</span></span> <span data-ttu-id="dc94f-184">Для сопоставления представления идентификации между доверенными доменами используется протокол WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="dc94f-184">It uses the WS-Trust protocol to map the identity representation from one trust domain to another.</span></span> <span data-ttu-id="dc94f-185">Федеративная привязка HTTP поддерживает безопасность SOAP, а также безопасность в смешанном режиме, но она не поддерживает безопасность транспорта.</span><span class="sxs-lookup"><span data-stu-id="dc94f-185">Federated HTTP binding supports SOAP security as well as mixed-mode security, but it does not support transport security.</span></span> <span data-ttu-id="dc94f-186">Службы, настроенные с использованием этой привязки, должны использовать транспорт HTTP.</span><span class="sxs-lookup"><span data-stu-id="dc94f-186">Services configured with this binding must use the HTTP transport.</span></span> <span data-ttu-id="dc94f-187">Дополнительные сведения см. в разделе [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="dc94f-187">For more information, see [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc94f-188">Пример</span><span class="sxs-lookup"><span data-stu-id="dc94f-188">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <ws2007FederationHttpBinding>
        <binding bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://www.contoso.com"
                 textEncoding="Utf16TextEncoding"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="None">
            <message negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"
                     issuedKeyType="PublicKey">
              <issuer address="http://localhost/Sts" />
            </message>
          </security>
        </binding>
      </ws2007FederationBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="dc94f-189">См. также</span><span class="sxs-lookup"><span data-stu-id="dc94f-189">See also</span></span>
- <xref:System.ServiceModel.WS2007FederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>
- [<span data-ttu-id="dc94f-190">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="dc94f-190">\<wsFederationHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)
- [<span data-ttu-id="dc94f-191">Привязки</span><span class="sxs-lookup"><span data-stu-id="dc94f-191">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="dc94f-192">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="dc94f-192">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="dc94f-193">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="dc94f-193">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="dc94f-194">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="dc94f-194">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
