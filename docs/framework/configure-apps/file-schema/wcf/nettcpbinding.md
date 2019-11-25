---
title: <netTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netTcpBinding Element
ms.assetid: 5c5104a7-8754-4335-8233-46a45322503e
ms.openlocfilehash: c43c141093c8287adb6d5a841a43ac893deefccd
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74139342"
---
# <a name="nettcpbinding"></a>\<netTcpBinding >

Задает безопасную, надежную и оптимизированную привязку, пригодную для обмена данными между компьютерами. По умолчанию создает стек связи среды выполнения с безопасностью Windows для защиты и проверки подлинности сообщений, с протоколом TCP для доставки сообщений, а также с кодированием двоичных сообщений.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)\
привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) >
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<netTcpBinding >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<netTcpBinding>
  <binding closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           listenBacklog="Integer"
           maxBufferPoolSize="integer"
           maxBufferSize="Integer"
           maxConnections="Integer"
           maxReceivedMessageSize="Integer"
           name="string"
           openTimeout="TimeSpan"
           portSharingEnabled="Boolean"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           transactionFlow="Boolean"
           transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="None/Transport/Message/Both">
      <message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
      <transport clientCredentialType="None/Windows/Certificate"
                 protectionLevel="None/Sign/EncryptAndSign" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a>Элементы и атрибуты

В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`closeTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:01:00.|  
|`hostNameComparisonMode`|Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов (URI). Это атрибут типа <xref:System.ServiceModel.HostNameComparisonMode>, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов (URI). Значение по умолчанию — <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, при котором имя узла в найденном соответствии не используется.|  
|`listenBacklog`|Положительное целое число, указывающее максимальное число каналов, ожидающих принятия прослушивателем. Соединения сверх этого лимита помещаются в очередь и обрабатываются по мере освобождения ресурсов. Атрибут `connectionTimeout` ограничивает время, в течение которого клиент ожидает установления соединения до создания исключения подключения. Значение по умолчанию — 10.|  
|`maxBufferPoolSize`|Целое число, задающее максимальный размер буферного пула для этой привязки. Значение по умолчанию - 512 * 1024 байт. Многие элементы Windows Communication Foundation (WCF) используют буферы. При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов. Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется. Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.|  
|`maxBufferSize`|Положительное целое число, указывающее максимальный размер буфера, используемого для хранения сообщений в памяти (в байтах).<br /><br /> Если атрибут `transferMode` имеет значение `Buffered`, этот атрибут должен быть равен значению атрибута `maxReceivedMessageSize`.<br /><br /> Если атрибут `transferMode` имеет значение `Streamed`, этот атрибут не может иметь значение большее, чем значение атрибута `maxReceivedMessageSize`, и должен иметь размер, по крайней мере равный размеру заголовков.<br /><br /> Значение по умолчанию — 65536. Для получения дополнительной информации см. <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.|  
|`maxConnections`|Целое число, указывающее максимальное число входящих и исходящих подключений, которые будут созданы/приняты службой. Входящие и исходящие подключения считаются относительно отдельного предела, определенного этим атрибутом.<br /><br /> Входящие соединения сверх указанного предела помещаются в очередь и обрабатываются по мере освобождения ресурсов.<br /><br /> Исходящие соединения сверх указанного предела помещаются в очередь и обрабатываются по мере освобождения ресурсов.<br /><br /> Значение по умолчанию — 10.|  
|`maxReceivedMessageSize`|Положительное целое число, задающее, в байтах, максимальный размер сообщения (включая заголовки), которое можно получить по каналу, настроенному с использованием этой привязки. Отправитель сообщения, превышающего это ограничение, получит ошибку SOAP. Получатель отклоняет сообщение и создает запись о событии в журнале трассировки. Значение по умолчанию — 65536.|  
|`name`|Строка, содержащая имя конфигурации привязки. Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки. Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя. Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
|`openTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:01:00.|  
|`portSharingEnabled`|Логическое значение, определяющее, включено ли совместное использование порта TCP для этого подключения. Если атрибут имеет значение `false`, для каждой привязки используется собственный порт. Этот параметр действителен только для служб, так как он не затрагивает клиенты.|  
|`receiveTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:10:00.|  
|`sendTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:01:00.|  
|`transactionFlow`|Логическое значение, определяющее, поддерживает ли привязка потоковые спецификации WS-Transactions. Значение по умолчанию: `false`.|  
|`transactionProtocol`|Указывает протокол транзакций, используемый с данной привязкой. Допустимы следующие значения:<br /><br /> -OleTransactions<br />-WSAtomicTransactionOctober2004<br /><br /> Значение по умолчанию - OleTransactions. Это атрибут типа <xref:System.ServiceModel.TransactionProtocol>.|  
|`transferMode`|Значение <xref:System.ServiceModel.TransferMode>, которое указывает, следует ли помещать сообщения в буфер или передавать их потоком по запросу или отклику.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> безопасности](security-of-nettcpbinding.md)|Определяет параметры безопасности привязки. Это элемент типа <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.|  
|[\<Реадеркуотас >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки. Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[\<reliableSession >](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|Указывает, устанавливаются ли между конечными точками канала надежные сеансы.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[привязки\<](bindings.md)|Этот элемент содержит коллекцию стандартных и пользовательских привязок.|  
  
## <a name="remarks"></a>Заметки

Эта привязка создает стек связи времени выполнения по умолчанию, использующий режим безопасности транспорта, протокол TCP для доставки сообщений, а также кодирование двоичных сообщений. Эта привязка является подходящей системой Windows Communication Foundation (WCF), предоставляемой для взаимодействия через интрасеть.  
  
 Конфигурация по умолчанию `netTcpBinding` выполняется быстрее, чем конфигурация, предоставляемая `wsHttpBinding`, но она предназначена только для взаимодействия WCF. Режим безопасности настраивается с помощью дополнительного атрибута `securityMode`. Использование WS-ReliableMessaging настраивается с использованием дополнительного атрибута `reliableSessionEnabled`. Но по умолчанию надежный обмен сообщениями отключен. В общем случае системные привязки по протоколу HTTP, такие как `wsHttpBinding` и `basicHttpBinding`, настроены на включение основных возможностей по умолчанию, в то время как привязка `netTcpBinding` по умолчанию отключает возможности, так что для получения поддержки, например для спецификаций WS-*, необходимо специально их включить. Это означает, что используемая по умолчанию конфигурация для TCP быстрее при обмене сообщениями между конечными точками, чем конфигурация по умолчанию для привязок HTTP.  
  
## <a name="example"></a>Пример

Привязка задается в файлах конфигурации для клиента и службы. Тип привязки указывается в атрибуте `binding` элемента `<endpoint>`. Если необходимо настроить привязку netTcpBinding и изменить некоторые из ее параметров, необходимо определить конфигурацию привязки. Конечная точка должна ссылаться на конфигурацию привязки с атрибутом `bindingConfiguration`. В следующем примере определяется конфигурация привязки.  
  
```xml  
<services>
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
    <endpoint address=""
              binding="netTcpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
    ...
  </service>
</services>
<bindings>
  <netTcpBinding>
    <binding closeTimeout="00:01:00"
             openTimeout="00:01:00"
             receiveTimeout="00:10:00"
             sendTimeout="00:01:00"
             transactionFlow="false"
             transferMode="Buffered"
             transactionProtocol="OleTransactions"
             hostNameComparisonMode="StrongWildcard"
             listenBacklog="10"
             maxBufferPoolSize="524288"
             maxBufferSize="65536"
             maxConnections="10"
             maxReceivedMessageSize="65536">
      <readerQuotas maxDepth="32"
                    maxStringContentLength="8192"
                    maxArrayLength="16384"
                    maxBytesPerRead="4096"
                    maxNameTableCharCount="16384" />
      <reliableSession ordered="true"
                       inactivityTimeout="00:10:00"
                       enabled="false" />
      <security mode="Transport">
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />
      </security>
    </binding>
  </netTcpBinding>
</bindings>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement>
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [> привязки \<](bindings.md)
