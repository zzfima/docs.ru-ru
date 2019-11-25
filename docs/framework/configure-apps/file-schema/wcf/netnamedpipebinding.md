---
title: <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 00a8580b-face-47a4-838d-b9fed48e72df
ms.openlocfilehash: f1aa68bcdda43fd77bee397c079695f7937faa52
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74139469"
---
# <a name="netnamedpipebinding"></a>\<netNamedPipeBinding >
Это безопасная и надежная привязка, оптимизированная для обмена данными между процессами компьютера. По умолчанию она создает стек связи среды выполнения, использующей WS-ReliableMessaging для обеспечения надежности, режим безопасности транспорта в целях безопасности передачи, именованные каналы для доставки сообщений, а также кодирование двоичных сообщений.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)\
привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) >
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<netNamedPipeBinding >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<netNamedPipeBinding>
  <binding closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxConnections="Integer"
           maxReceivedMessageSize="Integer"
           name="String"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           transactionFlow="Boolean"
           transactionProtocol="OleTransactions/WS-AtomicTransactionOctober2004"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|closeTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:01:00.|  
|hostNameComparisonMode|Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов (URI). Это атрибут типа <xref:System.ServiceModel.HostNameComparisonMode>, который указывает, используется ли имя узла для доступа к службе при сравнении по универсальному коду ресурсов (URI). Значение по умолчанию — <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, при котором имя узла в найденном соответствии не используется.|  
|maxBufferPoolSize|Целое число, задающее максимальный размер буферного пула для этой привязки. Значение по умолчанию - 524 288 байт (512 * 1024). Многие элементы Windows Communication Foundation (WCF) используют буферы. При создании буферов и их уничтожении после каждого использования расходуется слишком много ресурсов; при сборке мусора для буферов также расходуется слишком много ресурсов. Буферные пулы позволяют брать буфер из пула, использовать его, а затем возвращать обратно, когда он больше не требуется. Это позволяет избежать излишней нагрузки, связанной с созданием и уничтожением буферов.|  
|maxBufferSize|Положительное целое число, указывающее максимальный размер буфера, используемого для хранения сообщений в памяти (в байтах). Если буфер полон, избыточные данные остаются в основном сокете до тех пор, пока буфер не освободится. Данное значение не может быть меньше значения атрибута `maxReceivedMessageSize`. Значение по умолчанию — 65536. Для получения дополнительной информации см. <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.|  
|maxConnections|Целое число, указывающее максимальное число входящих и исходящих подключений, которые будут созданы/приняты службой. Входящие и исходящие подключения считаются относительно отдельного предела, определенного этим атрибутом.<br /><br /> Входящие соединения сверх указанного предела помещаются в очередь и обрабатываются по мере освобождения ресурсов.<br /><br /> Исходящие соединения сверх указанного предела помещаются в очередь и обрабатываются по мере освобождения ресурсов.<br /><br /> Значение по умолчанию — 10.|  
|maxReceivedMessageSize|Положительное целое число, задающее, в байтах, максимальный размер сообщения (включая заголовки), которое можно получить по каналу, настроенному с использованием этой привязки. Отправитель сообщения, превышающего это ограничение, получит ошибку SOAP. Получатель отклоняет сообщение и создает запись о событии в журнале трассировки. Значение по умолчанию — 65536.|  
|имя|Строка, содержащая имя конфигурации привязки. Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки. Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя. Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
|openTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:01:00.|  
|receiveTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:10:00.|  
|sendTimeout|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:01:00.|  
|transactionFlow|Логическое значение, определяющее, поддерживает ли привязка потоковые спецификации WS-Transactions. Значение по умолчанию: `false`.|  
|transactionProtocol|Указывает протокол транзакций, используемый с данной привязкой. Допустимы следующие значения:<br /><br /> -OleTransactions<br />-WS-AtomicTransactionOctober2004<br /><br /> Значение по умолчанию - OleTransactions. Это атрибут типа <xref:System.ServiceModel.TransactionProtocol>.|  
|transferMode|Значение <xref:System.ServiceModel.TransferMode>, которое указывает, следует ли помещать сообщения в буфер или передавать их потоком по запросу или отклику.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> безопасности](security-of-netnamedpipebinding.md)|Определяет параметры безопасности привязки. Это элемент типа <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>.|  
|[\<Реадеркуотас >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки. Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[привязки\<](bindings.md)|Этот элемент содержит коллекцию стандартных и пользовательских привязок.|  
  
## <a name="remarks"></a>Заметки  
 `NetNamedPipeBinding` создает стек связи среды выполнения по умолчанию, использующий режим безопасности транспорта, именованные каналы для доставки сообщений, а также кодирование двоичных сообщений. Эта привязка предоставляется системой Windows Communication Foundation (WCF) в качестве средства обмена данными на компьютере. Она также поддерживает транзакции.  
  
 Конфигурация по умолчанию для `NetNamedPipeBinding` аналогична конфигурации, предоставленной `NetTcpBinding`, но она существенно проще, поскольку реализация WCF предназначена только для использования в пределах компьютера и, следовательно, содержит меньшее число предоставляемых функциональных возможностей. Наиболее существенным отличием является то, что параметр `securityMode` содержит только значения `None` и `Transport`. Поддержка безопасности SOAP не предусмотрена. Режим безопасности настраивается с помощью дополнительного атрибута `securityMode`.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется применение привязки NetNamedPipeBinding, обеспечивающей обмен данными между процессами одного компьютера. Использование именованных каналов для обмена данными между компьютерами не поддерживается.  
  
 Привязка задается в файлах конфигурации для клиента и службы. Тип привязки указывается в атрибуте `binding` элемента `<endpoint>`. Чтобы настроить привязку netNamedPipeBinding и изменить некоторые ее параметры, необходимо определить конфигурацию привязки. Конечная точка должна ссылаться на конфигурацию привязки по имени с атрибутом `bindingConfiguration`. В этом примере конфигурации привязки присвоено имя «Binding1».  
  
```xml  
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <host>
          <baseAddresses>
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
          </baseAddresses>
        </host>
        <!-- this endpoint is exposed at the base address provided by host: net.pipe://localhost/ServiceModelSamples/service  -->
        <endpoint address="net.pipe://localhost/ServiceModelSamples/service"
                  binding="netNamedPipeBinding"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <bindings>
      <netNamedPipeBinding>
        <binding closeTimeout="00:01:00"
                 openTimeout="00:01:00"
                 receiveTimeout="00:10:00"
                 sendTimeout="00:01:00"
                 transactionFlow="false"
                 transferMode="Buffered"
                 transactionProtocol="OleTransactions"
                 hostNameComparisonMode="StrongWildcard"
                 maxBufferPoolSize="524288"
                 maxBufferSize="65536"
                 maxConnections="10"
                 maxReceivedMessageSize="65536">
          <security mode="Transport">
            <transport protectionLevel="EncryptAndSign" />
          </security>
        </binding>
      </netNamedPipeBinding>
    </bindings>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement>
- <xref:System.ServiceModel.NetNamedPipeBinding>
- [> привязки \<](bindings.md)
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
