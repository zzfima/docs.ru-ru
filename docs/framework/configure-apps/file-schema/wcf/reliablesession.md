---
title: <reliableSession>
ms.date: 03/30/2017
ms.assetid: 129b4a59-37f0-4030-b664-03795d257d29
ms.openlocfilehash: 95f6646041dc2dd7bae7691a0a9f748c844f50b6
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738746"
---
# <a name="reliablesession"></a>\<reliableSession >
Определяет параметры протокола WS-Reliable Messaging. Когда этот элемент добавляется к пользовательской привязке, получаемый канал может поддерживать гарантии доставки только один раз.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)\
привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) >
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<reliableSession >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<reliableSession acknowledgementInterval="TimeSpan"
                 flowControlEnabled="Boolean"
                 inactivityTimeout="TimeSpan"
                 maxPendingChannels="Integer"
                 maxRetryCount="Integer"
                 maxTransferWindowSize="Integer"
                 reliableMessagingVersion="Default/WSReliableMessagingFebruary2005/WSReliableMessaging11"
                 ordered="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|acknowledgementInterval|Атрибут <xref:System.TimeSpan> задает максимальный временной интервал, в течение которого канал ожидает перед отправлением уведомления о сообщениях, которые уже приняты к этому времени. Значение по умолчанию - 00:00:0.2.|  
|flowControlEnabled|Логическое значение, которое указывает, активировано ли расширенное управление потоком, то есть собственная реализация Microsoft управления потоком для WS-Reliable Messaging. Значение по умолчанию: `true`.|  
|inactivityTimeout|Атрибут <xref:System.TimeSpan> указывает максимальную длительность, в течение которой канал позволяет другим участникам соединения не отправлять никаких сообщений, до закрытия канала с ошибкой. Значение по умолчанию - 00:10:00.<br /><br /> Под активностью канала понимается получение сообщений от приложения или инфраструктуры. Данное свойство задает максимальный промежуток времени, в течение которого поддерживается неактивный сеанс. Если период неактивности превышает установленное ограничение, сеанс прерывается инфраструктурой, и канал закрывается с ошибкой. **Примечание.**  Приложение не является обязательным для периодической отправки сообщений, чтобы поддерживать подключение.|  
|maxPendingChannels|Целое число, задающее максимальное число каналов, ожидающих принятия на прослушивателе. Это значение должно быть в диапазоне от 1 до 16 384 включительно. Значение по умолчанию — 4.<br /><br /> Каналы находятся в режиме ожидания перед принятием. По достижении этого предела каналы больше не создаются. Вместо этого они переводятся в режим ожидания до тех пор, пока их число не снизится (по мере принятия ожидающих каналов). Этот предел задается отдельно для каждой фабрики.<br /><br /> Когда достигается пороговое значение и удаленное приложение пытается установить новый надежный сеанс, запрос отклоняется, и открытая операция, инициировавшая запрос, завершается с ошибкой. Данное ограничение не действует в отношении числа ожидающих исходящих каналов.|  
|maxRetryCount|Целое число, которое определяет максимальное количество попыток повторной передачи надежным каналом сообщения, для которого не было получено подтверждение приема. Повторная передача осуществляется посредством вызова функции Send в основном канале.<br /><br /> Значение должно быть больше нуля. Значение по умолчанию — 8.<br /><br /> Значение должно целым числом больше нуля. Если подтверждение приема не будет получено после последней попытки повторной передачи, канал закрывается с ошибкой.<br /><br /> Сообщение считается переданным, если получатель подтвердил получение этого сообщения, отправив соответствующее подтверждение отправителю.<br /><br /> Если для переданного сообщения уведомление не было получено в течение отведенного времени, инфраструктура автоматически передает сообщение повторно. Количество попыток, предпринимаемых инфраструктурой для повторной передачи сообщения, не превышает того значения, которое задано данным свойством. Если подтверждение приема не будет получено после последней попытки повторной передачи, канал закрывается с ошибкой.<br /><br /> Инфраструктура использует алгоритм с экспоненциальной задержкой для определения времени повторной передачи на основании вычисленного среднего значения времени кругового пути. Задержка перед первой попыткой повторной передачи составляет 1 секунду, однако для каждой последующей попытки время задержки удваивается. Таким образом, временной интервал между первой и последней попытками составляет около 8,5 минут. Время первой повторной передачи определяется с учетом вычисленного значением времени кругового пути, соответственно изменяется общая длительность всех задержек. Это позволяет динамически адаптировать время между попытками повторной передачи в соответствии с условиями сети.|  
|maxTransferWindowSize|Целое число, задающее максимальный размер буфера. Допустимые значения находятся в диапазоне от 1 до 4096 включительно.<br /><br /> Для клиента данный атрибут определяет максимальный размер буфера, используемого надежным каналом для хранения сообщений, получение которых еще не подтверждено получателем. Единицей квоты является одно сообщение. Если буфер полон, дальнейшее выполнение операций SEND блокируется.<br /><br /> Для получателя этот атрибут определяет максимальный размер буфера, используемого каналом для хранения входящих сообщений, которые еще не переданы приложению. Если буфер заполнен, поступающие сообщения автоматически отбрасываются получателем и требуют повторной передачи со стороны клиента.|  
|упорядоченного|Логическое значение, определяющее, прибывают ли сообщения точно в том порядке, в котором они были отправлены. Если данному атрибуту присвоено значение `false`, порядок получения сообщений может не соблюдаться. Значение по умолчанию: `true`.|  
|reliableMessagingVersion|Допустимое значение из <xref:System.ServiceModel.ReliableMessagingVersion>, задающее версию используемого протокола WS-ReliableMessaging.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[> привязки \<](bindings.md)|Определяет все возможности пользовательской привязки.|  
  
## <a name="remarks"></a>Заметки  
 Надежные сеансы обеспечивают возможности для надежного обмена сообщениями и сеансов. При надежном обмене сообщениями в случае сбоя предпринимается повторная попытка передачи, и можно задать такие гарантии доставки, как соблюдение порядка получения сообщений. Сеансы поддерживают состояние для клиентов между вызовами. Этот элемент также дополнительно предоставляет упорядоченную доставку сообщений. Эта реализация сеанса может использоваться в контексте посредников SOAP и транспорта.  
  
 Каждый элемент привязки представляет собой этап обработки при отправке или получении сообщений. Во время выполнения элементы привязки создают фабрики и прослушиватели каналов, которые нужны для построения стеков исходящих и входящих каналов, необходимых для приема и передачи сообщений. Элемент `reliableSession` предоставляет дополнительный уровень в стеке, который может установить надежный сеанс между конечными точками и настроить поведение этого сеанса.  
  
 Дополнительные сведения см. в разделе [Надежные сеансы](../../../wcf/feature-details/reliable-sessions.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как настраивать пользовательскую привязку с различными элементами транспорта и кодирования сообщений, а именно: с обеспечением надежных сеансов, которые поддерживают состояние клиента и задают гарантии соблюдения очередности доставки сообщений. Эта функция настраивается в файлах конфигурации приложения для клиента и службы. В следующем примере демонстрируется конфигурация службы.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by host: http://localhost/servicemodelsamples/service.svc -->
        <!-- specify customBinding binding and a binding configuration to use -->
        <endpoint address=""
                  binding="customBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <!-- custom binding configuration - configures HTTP transport, reliable sessions -->
    <bindings>
      <customBinding>
        <binding name="Binding1">
          <reliableSession />
          <security authenticationMode="SecureConversation"
                    requireSecurityContextCancellation="true">
          </security>
          <compositeDuplex />
          <oneWay />
          <textMessageEncoding messageVersion="Soap12WSAddressing10"
                               writeEncoding="utf-8" />
          <httpTransport authenticationScheme="Anonymous"
                         bypassProxyOnLocal="false"
                         hostNameComparisonMode="StrongWildcard"
                         proxyAuthenticationScheme="Anonymous"
                         realm=""
                         useDefaultWebProxy="true" />
        </binding>
      </customBinding>
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

- <xref:System.ServiceModel.Configuration.ReliableSessionElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
- [Надежные сеансы](../../../wcf/feature-details/reliable-sessions.md)
- [Привязки](../../../wcf/bindings.md)
- [Расширение привязок](../../../wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
