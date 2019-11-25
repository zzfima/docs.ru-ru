---
title: <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: a68b44d7-7799-43a3-9e63-f07c782810a6
ms.openlocfilehash: 7456c6373c64e07b73e15e7e2bb229dce4032121
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140748"
---
# <a name="netmsmqbinding"></a>\<netMsmqBinding >
Определяет поставленную в очередь привязку, пригодную для обеспечения связи между компьютерами.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)\
привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) >
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<netMsmqBinding >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<netMsmqBinding>
  <binding closeTimeout="TimeSpan"
           customDeadLetterQueue="Uri"
           deadLetterQueue="Uri"
           durable="Boolean"
           exactlyOnce="Boolean"
           maxBufferPoolSize="Integer"
           maxReceivedMessageSize="Integer"
           maxRetryCycles="Integer"
           name="String"
           openTimeout="TimeSpan"
           poisonMessageHandling="Disabled/EnabledIfSupported"
           queueTransferProtocol="Native/Srmp/SrmpSecure"
           receiveErrorHandling="Drop/Fault/Move/Reject"
           receiveTimeout="TimeSpan"
           receiveRetryCount="Integer"
           rejectAfterLastRetry="Boolean"
           retryCycleDelay="TimeSpan"
           sendTimeout="TimeSpan"
           timeToLive="TimeSpan"
           useActiveDirectory="Boolean"
           useMsmqTracing="Boolean"
           useSourceJournal="Boolean">
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/InfoCard" />
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`closeTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:01:00.|  
|`customDeadLetterQueue`|Универсальный код ресурса (URI), который указывает местоположение очереди недоставленных сообщений для каждого приложения, куда помещаются сообщения с истекшим сроком или сообщения, которые не удалось передать или доставить.<br /><br /> Очередью недоставленных сообщений является очередь в диспетчере очередей отправившего приложения для сообщений с истекшим сроком, которые не удалось доставить.<br /><br /> Универсальный код ресурса (URI), определяемый свойством <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A>, должен использовать схему net.msmq.|  
|`deadLetterQueue`|Значение <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A>, определяющее, какой тип очереди недоставленных сообщений следует использовать, если таковые имеются.<br /><br /> Очередь недоставленных сообщений - это место, куда будут помещаться сообщения, доставка которых приложению завершилась неудачей.<br /><br /> Для сообщений с требованием гарантии доставки `exactlyOnce` (т.е. если для атрибута `exactlyOnce` установлено значение `true`) в качестве этого атрибута в рамках всей системы по умолчанию устанавливается очередь недоставленных транзакционных сообщений в MSMQ.<br /><br /> Для сообщений, которые не требуют гарантии, по умолчанию этот атрибут имеет значение `null`.|  
|`durable`|Логическое значение, указывающее, является ли сообщение в очереди постоянным или переменным. Постоянное сообщение сохраняется после сбоя диспетчера очередей, а переменное сообщение — нет. Переменные сообщения используются, если для приложений требуются небольшие задержки, и приложения допускают периодические потери сообщений. Если атрибут `exactlyOnce` имеет значение `true`, сообщения должны быть постоянными. Значение по умолчанию: `true`.|  
|`exactlyOnce`|Логическое значение, указывающее, доставляется ли каждое сообщение, обрабатываемое этой привязкой, только один раз. Затем отправитель оповещается об ошибках доставки. Если `durable` имеет значение `false`, этот атрибут не учитывается и сообщения пересылаются без гарантии доставки. Значение по умолчанию: `true`. Для получения дополнительной информации см. <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>.|  
|`maxBufferPoolSize`|Целое число, задающее максимальный размер буферного пула для этой привязки. Значение по умолчанию — 8.|  
|`maxReceivedMessageSize`|Положительное целое число, определяющее максимальный размер сообщения (в байтах), включая заголовки, которое обрабатывается этой привязкой. Отправитель сообщения, превышающего это ограничение, получит ошибку SOAP. Получатель отклоняет сообщение и создает запись о событии в журнале трассировки. Значение по умолчанию — 65536. Это ограничение размера сообщения предназначено для уменьшения уязвимости к атакам типа «отказ в обслуживании» (DoS).|  
|`maxRetryCycles`|Целое число, указывающее количество циклов повтора, используемых возможностью обнаружения подозрительных сообщений. Сообщение становится подозрительным, если попытки доставки во всех циклах закончились неудачей. Значение по умолчанию — 3. Для получения дополнительной информации см. <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A>.|  
|`name`|Обязательный атрибут. Строка, содержащая имя конфигурации привязки. Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки. Начиная с .NET Framework 4, привязки и поведения не обязательно должны иметь имя. Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
|`openTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:01:00.|  
|`QueueTransferProtocol`|Допустимое значение <xref:System.ServiceModel.QueueTransferProtocol>, задающее поставленный в очередь транспорт коммуникационного канала, используемый этой привязкой. MSMQ не поддерживает адресацию Active Directory при использовании протокола надежного обмена сообщениями SOAP. Поэтому не следует присвоить этому атрибуту значение `Srmp` или `Srmps`, если атрибуту `useActiveDirectory` присвоено значение `true`.|  
|`receiveErrorHandling`|Значение <xref:System.ServiceModel.ReceiveErrorHandling>, указывающее, каким образом будут обрабатываться подозрительные сообщения и сообщения, которые не удалось доставить.|  
|`receiveRetryCount`|Целое число, задающее максимальное число попыток отправки сообщения диспетчером очереди, после которого сообщение передается в очередь повторного выполнения.|  
|`receiveTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:10:00.|  
|`retryCycleDelay`|Значение TimeSpan, которое задает временную задержку между циклами повторов при попытке доставить сообщение, которое не удалось доставить сразу. Значение определяет только минимальное время ожидания, поскольку фактическое время ожидания может быть больше. Значение по умолчанию - 00:10:00. Для получения дополнительной информации см. <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A>.|  
|`sendTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:01:00.|  
|`timeToLive`|Значение TimeSpan, указывающее, как долго сообщения остаются действительными до истечения их срока, после чего они переводятся в очередь недоставленных сообщений. Значение по умолчанию - 1.00:00:00.<br /><br /> Этот атрибут устанавливается для предотвращения устаревания срочных сообщений до их обработки получающими приложениями. Сообщение в очереди, которое не поступает в принимающее приложение в пределах заданного интервала времени, считается устаревшим. Устаревшие сообщения отправляются в специальную очередь, называемую очередью недоставленных сообщений. Расположение очереди недоставленных сообщений задается атрибутом `DeadLetterQueue`, или оно устанавливается на основании гарантий в соответствующее значение по умолчанию.|  
|`usingActiveDirectory`|Логическое значение, определяющее, должны ли адреса очередей преобразовываться с использованием Active Directory.<br /><br /> Адреса очередей MSMQ могут включать имена пути или непосредственные имена форматов. С помощью непосредственного имени формата служба MSMQ разрешает имя компьютера с использованием DNS, NetBIOS или IP-адреса. С помощью имени пути MSMQ разрешает имя компьютера с использованием Active Directory.<br /><br /> По умолчанию в Windows Communication Foundation (WCF) транспортный транспорт преобразует URI очереди сообщений в прямое имя формата. Установив свойство `UseActiveDirectory` на значение true, приложение может указать, что транспорт в очереди должен разрешать имя компьютера с использованием Active Directory, а не DNS, NetBIOS или IP.|  
|`useMsmqTracing`|Логическое значение, указывающее, должна ли выполняться трассировка сообщений, обрабатываемых этой привязкой. Значение по умолчанию: `false`. Если трассировка включена, каждый раз, когда сообщение отправляется с компьютера службы очередей или поступает на этот компьютер, создаются сообщения-отчеты, которые затем отправляются в очередь отчетов.|  
|`useSourceJournal`|Логическое значение, которое указывает, должны ли копии сообщений, обрабатываемых этой привязкой, храниться в журнале источников. Значение по умолчанию: `false`.<br /><br /> Использующие очереди приложения, которым нужно хранить запись сообщений, покинувших очередь исходящих сообщений компьютера, могут копировать сообщения в журнал компьютера. После того как сообщение покинуло очередь исходящих сообщений, и появилось подтверждение приема сообщения конечным компьютером, в очереди системного журнала компьютера-отправителя сохраняется копия сообщения.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Реадеркуотас >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки. Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[\<> безопасности](security-of-netmsmqbinding.md)|Определяет параметры безопасности привязки. Это элемент типа <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[привязки\<](bindings.md)|Этот элемент содержит коллекцию стандартных и пользовательских привязок.|  
  
## <a name="remarks"></a>Заметки  
 Привязка `netMsmqBinding` обеспечивает поддержку организации очереди, используя очередь сообщений (MSMQ) как транспорт, и включает поддержку слабо связанных приложений, изоляции сбоев, распределения нагрузки, а также операций при отсутствии подключения к сети. Описание этих функций см. [в разделе очереди в WCF](../../../wcf/feature-details/queues-in-wcf.md).  
  
## <a name="example"></a>Пример  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <netMsmqBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 deadLetterQueue="net.msmq://localhost/blah"
                 durable="true"
                 exactlyOnce="true"
                 maxReceivedMessageSize="1000"
                 maxRetries="11"
                 maxRetryCycles="12"
                 poisonMessageHandling="Disabled"
                 rejectAfterLastRetry="false"
                 retryCycleDelay="00:05:55"
                 timeToLive="00:11:11"
                 sourceJournal="true"
                 useMsmqTracing="true"
                 useActiveDirectory="true">
          <security>
            <message clientCredentialType="Windows" />
          </security>
        </binding>
      </netMsmqBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement>
- [> привязки \<](bindings.md)
- [Привязки](../../../wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [Очереди в WCF](../../../wcf/feature-details/queues-in-wcf.md)
