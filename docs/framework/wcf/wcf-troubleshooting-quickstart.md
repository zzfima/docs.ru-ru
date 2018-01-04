---
title: "Примеры устранения неполадок WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], troubleshooting
- Windows Communication Foundation [WCF], troubleshooting
ms.assetid: a9ea7a53-f31a-46eb-806e-898e465a4992
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 37b8ff108cb9ddb0df8ff4cb365ae543959546cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-troubleshooting-quickstart"></a>Примеры устранения неполадок WCF
В этом разделе приведено несколько известных проблем, с которыми столкнулись пользователи при разработке клиентов и служб WCF. Если проблема, с которой столкнулись вы, отсутствует в этом списке, рекомендуется настроить трассировку для данной службы. При этом будет создан файл трассировки, который можно просмотреть с помощью средства просмотра файлов трассировки и получить подробные сведения об исключениях, которые могут возникать в службе. Дополнительные сведения о настройке трассировки см. в разделе [Configuring Tracing](../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md). Дополнительные сведения о средстве просмотра файлов трассировки см. в разделе [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).  
  
1.  [После установки Windows 7 и IIS при попытке перейти к службе WCF выдается следующее сообщение об ошибке: «Ошибка HTTP 404.3 - не найдено»](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#bkmk_0)  
  
     Ошибка HTTP 404.3 - не найдено. Запрашиваемая страница не может быть выдана из-за конфигурации расширения. Если страница - скрипт, добавьте обработчик. Если файл должен загружаться, добавьте MIME-сопоставление. Подробное описание ошибки InformationModule StaticFileModule.  
  
2.  [Иногда при втором запросе возникает исключение MessageSecurityException, если клиент бездействует некоторое время после первого запроса. В чем причина?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q1)  
  
3.  [Когда со службой взаимодействует около 10 клиентов, она отклоняет подключение новых клиентов. В чем причина?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q2)  
  
4.  [Можно ли загружать конфигурацию службы из расположения, отличного от файла конфигурации приложения WCF?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q3)  
  
5.  [Служба и клиент работают нормально, но их не удается запустить, если клиент находится на другом компьютере. В чем причина?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q4)  
  
6.  [При создании FaultException\<исключение > там, где типом является исключение, всегда получает общего FaultException на стороне клиента, а не универсального типа. В чем причина?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q5)  
  
7.  [Создается впечатление, что односторонние операции, а также операции запроса-ответа возвращаются примерно с той же скоростью, что и ответы без данных. В чем причина?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q6)  
  
8.  [В службе используется сертификат X.509, при этом получается исключение System.Security.Cryptography.CryptographicException. В чем причина?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q77)  
  
9. [В имени первого параметра операции прописные буквы были заменены на строчные, и теперь клиент выдает исключение. В чем причина?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q88)  
  
10. [При использовании одного из средств трассировки получено исключение EndpointNotFoundException. В чем причина?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q99)  
  
11. [При вызове веб-приложения HTTP WCF из приложения службы протокола SOAP WCF возвращается следующая ошибка: «405 Метод запрещен»](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BK_MK99)  
  
 [Что такое базовый адрес? Как он связан с адресом конечной точки?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q10)  
  
<a name="bkmk_0"></a>   
## <a name="after-installing-windows-7-and-iis-when-i-attempt-to-browse-to-a-wcf-service-i-get-the-following-error-message-http-error-4043--not-found"></a>После установки Windows 7 и IIS при попытке перейти к службе WCF выдается следующее сообщение об ошибке: «Ошибка HTTP 404.3 - не найдено»  
 Полное сообщение об ошибке:  
  
 Ошибка HTTP 404.3 - не найдено. Запрашиваемая страница не может быть выдана из-за конфигурации расширения. Если страница - скрипт, добавьте обработчик. Если файл должен загружаться, добавьте MIME-сопоставление. Подробное описание ошибки InformationModule StaticFileModule.  
  
 Это сообщение об ошибке возникает, если «Активация Windows Communication Foundation HTTP» не задана явно на панели управления. Чтобы установить этот параметр, перейдите на панель управления и выберите «Программы» в левом нижнем углу окна. Установите переключатель «Включение компонентов Windows». Разверните элемент Microsoft .NET Framework 3.5.1 и выберите «Активация Windows Communication Foundation по HTTP».  
  
<a name="BKMK_q1"></a>   
## <a name="sometimes-i-receive-a-messagesecurityexception-on-the-second-request-if-my-client-is-idle-for-a-while-after-the-first-request-what-is-happening"></a>Иногда при втором запросе возникает исключение MessageSecurityException, если клиент бездействует некоторое время после первого запроса. В чем причина?  
 Сбой второго запроса может произойти по двум причинам: (1) истекло время ожидания сеанса или (2) перезапущен веб-сервер, на котором размещена служба. В первом случае сеанс действителен до того, как истечет время ожидания службы. Если служба не получает запрос от клиента в течение времени, заданного в привязке службы (<xref:System.ServiceModel.Channels.Binding.ReceiveTimeout%2A>), служба завершает сеанс безопасности. Последующие сообщения клиента приводят к исключению <xref:System.ServiceModel.Security.MessageSecurityException>. Клиент должен повторно установить безопасный сеанс со службой, чтобы отправлять будущие сообщения, или использовать маркер контекста безопасности с отслеживанием состояния. Токены контекста безопасности с отслеживанием состояния также позволяют защитить сеанс во время перезапуска веб-сервера. [!INCLUDE[crabout](../../../includes/crabout-md.md)]использовании токенов контекста с отслеживанием состояния безопасности в безопасном сеансе см [как: создание токена контекста безопасности для безопасного сеанса](../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md). Кроме того, можно отключить безопасные сеансы. При использовании [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) привязки, можно задать `establishSecurityContext` свойства `false` Чтобы отключить безопасные сеансы. Чтобы отключить безопасные сеансы для других привязок, необходимо создать пользовательскую привязку. Подробные сведения о создании пользовательской привязки см. в разделе [How to: Create a Custom Binding Using the SecurityBindingElement](../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md). Перед применением этих параметров необходимо разобраться с требованиями безопасности приложения.  
  
<a name="BKMK_q2"></a>   
## <a name="my-service-starts-to-reject-new-clients-after-about-10-clients-are-interacting-with-it-what-is-happening"></a>Когда со службой взаимодействует около 10 клиентов, она отклоняет подключение новых клиентов. В чем причина?  
 По умолчанию службы поддерживают не более 10 параллельных сеансов. Поэтому при использовании в привязках службы сеансов, служба принимает подключения новых клиентов до достижения этого числа. После этого служба отклоняет подключения новых клиентов, пока не будет закрыт один из текущих сеансов. Поддержку большего количества клиентов можно обеспечить несколькими способами. Если для службы не требуются сеансы, не используйте сеансовую привязку. ([!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Сеансы, использующие](../../../docs/framework/wcf/using-sessions.md).) Можно также увеличить ограничение сеансов, установив подходящее значение для свойства <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>.  
  
<a name="BKMK_q3"></a>   
## <a name="can-i-load-my-service-configuration-from-somewhere-other-than-the-wcf-applications-configuration-file"></a>Можно ли загружать конфигурацию службы из расположения, отличного от файла конфигурации приложения WCF?  
 Да, но необходимо создать пользовательский класс <xref:System.ServiceModel.ServiceHost> , переопределяющий метод <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> . Внутри этого метода можно вызвать базовый класс, чтобы сначала загрузить конфигурацию (если дополнительно требуется загрузить сведения о стандартной конфигурации), но можно также полностью заменить систему загрузки конфигурации. Обратите внимание, что если требуется загрузить конфигурацию из файла, отличного от файла конфигурации приложения, необходимо самостоятельно выполнять анализ файла и загрузить конфигурацию.  
  
 В следующем примере кода показано, как переопределить метод <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> и напрямую настроить конечную точку.  
  
```csharp
public class MyServiceHost : ServiceHost  
{  
    public MyServiceHost(Type serviceType, params Uri[] baseAddresses)    
      : base(serviceType, baseAddresses)  
    {
        Console.WriteLine("MyServiceHost Constructor");
    }  
  
    protected override void ApplyConfiguration()  
    {  
        string straddress = GetAddress();  
        Uri address = new Uri(straddress);  
        Binding binding = GetBinding();  
        base.AddServiceEndpoint(typeof(IData), binding, address);  
    }  
  
    string GetAddress()  
    {
        return "http://MyMachine:7777/MyEndpointAddress/";
    }  
  
    Binding GetBinding()  
    {  
        WSHttpBinding binding = new WSHttpBinding();  
        binding.Security.Mode = SecurityMode.None;  
        return binding;  
    }  
}  
```  
  
<a name="BKMK_q4"></a>   
## <a name="my-service-and-client-work-great-but-i-cant-get-them-to-work-when-the-client-is-on-another-computer-whats-happening"></a>Служба и клиент работают нормально, но их не удается запустить, если клиент находится на другом компьютере. В чем причина?  
 В зависимости от исключения возможны следующие причины.  
  
-   Возможно, потребуется использовать для адреса конечной точки клиента имя узла, а не "localhost".  
  
-   Возможно, для приложения потребуется открыть порт. Дополнительные сведения см. в разделе [Firewall Instructions](../../../docs/framework/wcf/samples/firewall-instructions.md) примеров SDK.  
  
-   Другие возможные причины этой проблемы см. в разделе примеров [Running the Samples in a Workgroup and Across Machines](http://msdn.microsoft.com/en-us/a451a525-e7ce-452d-9da9-620221260113).  
  
-   Если в клиенте используются учетные данные Windows и создается исключение <xref:System.ServiceModel.Security.SecurityNegotiationException>, настройте Kerberos, как указано ниже.  
  
    1.  Добавьте учетные данные идентификации в элемент конечной точки в файле конфигурации клиента App.config.  
  
        ```xml
        <endpoint   
          address="http://MyServer:8000/MyService/"   
          binding="wsHttpBinding"   
          bindingConfiguration="WSHttpBinding_IServiceExample"   
          contract="IServiceExample"   
          behaviorConfiguration="ClientCredBehavior"   
          name="WSHttpBinding_IServiceExample">  
          <identity>  
            <userPrincipalName value="name@corp.contoso.com"/>  
          </identity>  
        </endpoint>  
        ```  
  
    2.  Для этого запустите службу от имени учетной записи System или NetworkService. Чтобы создать командное окно в учетной записи System, выполните следующую команду.  
  
        ```console
        at 12:36 /interactive "cmd.exe"  
        ```  
  
    3.  Разместите службу в службах IIS, которые по умолчанию используют учетную запись имени участника службы (SPN).  
  
    4.  Зарегистрируйте в домене новое имя участника службы (SPN) с помощью программы SetSPN. Обратите внимание, что для этого потребуются права администратора домена.  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)] протоколе Kerberos см. в разделе [Security Concepts Used in WCF](../../../docs/framework/wcf/feature-details/security-concepts-used-in-wcf.md) и:  
  
-   [Отладка ошибок проверки подлинности Windows](../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
  
-   [Регистрация имен субъектов-служб Kerberos в файле Http.sys](http://go.microsoft.com/fwlink/?LinkId=86943)  
  
-   [Сведения о Kerberos](http://go.microsoft.com/fwlink/?LinkId=86946)  
  
<a name="BKMK_q5"></a>   
## <a name="when-i-throw-a-faultexceptionexception-where-the-type-is-an-exception-i-always-receive-a-general-faultexception-type-on-the-client-and-not-the-generic-type-whats-happening"></a>При создании FaultException\<исключение > там, где типом является исключение, всегда получает общего FaultException на стороне клиента, а не универсального типа. В чем причина?  
 Настоятельно рекомендуется создать свой собственный пользовательский тип данных об ошибке и объявить его в качестве типа сведений в контракте сбоя. Это необходимо, так как при использовании типов исключений, предоставляемых системой, могут возникнуть следующие проблемы.  
  
-   Создается зависимость типов, которая не дает возможности воспользоваться одним из главных преимуществ приложений, ориентированных на службы.  
  
-   Не удается воспользоваться стандартной сериализацией исключений. Некоторые из них, например <xref:System.Security.SecurityException>, могут вообще не сериализоваться.  
  
-   Внутренние сведения сериализации доступны для клиентов. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Задание и обработка сбоев в контрактах и службах](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
 Однако при отладке приложения можно сериализовать сведения об исключении и возвратить их клиенту с помощью класса <xref:System.ServiceModel.Description.ServiceDebugBehavior> .  
  
<a name="BKMK_q6"></a>   
## <a name="it-seems-like-one-way-and-request-reply-operations-return-at-roughly-the-same-speed-when-the-reply-contains-no-data-whats-happening"></a>Создается впечатление, что односторонние операции, а также операции запроса-ответа возвращаются примерно с той же скоростью, что и ответы без данных. В чем причина?  
 Если указывается, что операция является односторонней, это лишь означает, что контракт операции принимает входящее сообщение и не возвращает выходное сообщение. В [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]все вызовы клиентов возвращаются, когда исходящие данные переданы по каналам связи или возникло исключение. Односторонние операции выполняются таким же образом, и они могут создавать исключение, если не удается обнаружить службу, или заблокировать выполнение, если служба не готова к приему данных из сети. В [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]односторонние вызовы обычно возвращаются к клиенту быстрее, чем операции запроса-ответа. Однако любое условие, замедляющее отправку исходящих данных по сети, одинаково замедляет как односторонние операции, так и операции запроса-ответа. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Односторонние службы](../../../docs/framework/wcf/feature-details/one-way-services.md) и [доступ к службам с помощью клиента WCF](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md).  
  
<a name="BKMK_q77"></a>   
## <a name="im-using-an-x509-certificate-with-my-service-and-i-get-a-systemsecuritycryptographycryptographicexception-whats-happening"></a>В службе используется сертификат X.509, при этом получается исключение System.Security.Cryptography.CryptographicException. В чем причина?  
 Обычно это происходит после изменения учетной записи пользователя, в которой выполняется рабочий процесс IIS. Например, эта ошибка может возникнуть в [!INCLUDE[wxp](../../../includes/wxp-md.md)]при изменении учетной записи по умолчанию, в которой выполняется процесс Aspnet_wp.exe, с ASPNET на пользовательскую учетную запись. Если используется закрытый ключ, его процесс должен иметь разрешение для доступа к файлу с этим ключом.  
  
 В этом случае необходимо предоставить учетной записи процесса права доступа для чтения файла с закрытым ключом. Например, если рабочий процесс IIS выполняется в учетной записи Бориса, ему необходимо предоставить права доступа для чтения файла, содержащего закрытый ключ.  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)] том, как предоставить нужной учетной записи пользователя доступ к файлу с закрытым ключом для конкретного сертификата X.509, см. разделе [How to: Make X.509 Certificates Accessible to WCF](../../../docs/framework/wcf/feature-details/how-to-make-x-509-certificates-accessible-to-wcf.md).  
  
<a name="BKMK_q88"></a>   
## <a name="i-changed-the-first-parameter-of-an-operation-from-uppercase-to-lowercase-now-my-client-throws-an-exception-whats-happening"></a>В имени первого параметра операции прописные буквы были заменены на строчные, и теперь в клиенте выдается исключение. В чем причина?  
 Значения имен параметров в сигнатуры операции являются частью контракта и чувствительны к регистру. Используйте атрибут <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>, чтобы различать имя локального параметра и метаданные, описывающие операцию для клиентских приложений.  
  
<a name="BKMK_q99"></a>   
## <a name="im-using-one-of-my-tracing-tools-and-i-get-an-endpointnotfoundexception-whats-happening"></a>При использовании одного из средств трассировки получено исключение EndpointNotFoundException. В чем причина?  
 Если используется средство трассировки, отличное от механизма трассировки по умолчанию в [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] и получено исключение <xref:System.ServiceModel.EndpointNotFoundException> , указывающее на несоответствие фильтра адресов, необходимо задействовать класс <xref:System.ServiceModel.Description.ClientViaBehavior> , чтобы направить сообщения в средство трассировки для их дальнейшего перенаправления на адрес службы. Класс <xref:System.ServiceModel.Description.ClientViaBehavior> изменяет заголовок адресации `Via` , чтобы задать следующий сетевой адрес отдельно от конечного получателя, указанного заголовком адресации `To` . Однако при этом не следует изменять адрес конечной точки, используемый для установки значения `To` .  
  
 В следующем примере кода показан пример файла конфигурации клиента.  
  
```xml
<endpoint   
  address=http://localhost:8000/MyServer/  
  binding="wsHttpBinding"  
  bindingConfiguration="WSHttpBinding_IMyContract"  
  behaviorConfiguration="MyClient"   
  contract="IMyContract"   
  name="WSHttpBinding_IMyContract">  
</endpoint>  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="MyClient">  
      <clientVia viaUri="http://localhost:8001/MyServer/"/>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
```  
  
<a name="BKMK_q10"></a>   
## <a name="what-is-the-base-address-how-does-it-relate-to-an-endpoint-address"></a>Что такое базовый адрес? Как он связан с адресом конечной точки?  
 Базовый адрес - это корневой адрес для класса <xref:System.ServiceModel.ServiceHost> . По умолчанию, если в конфигурацию службы добавлен класс <xref:System.ServiceModel.Description.ServiceMetadataBehavior> , язык описания веб-служб (WSDL) для всех конечных точек, публикуемых узлом, извлекается из базового HTTP-адреса, относительного адреса, предоставленного поведением метаданных, а также "?wsdl". Если вы знакомы с [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] и IIS, базовый адрес эквивалентен виртуальному каталогу.  
  
## <a name="sharing-a-port-between-a-service-endpoint-and-a-mex-endpoint-using-the-nettcpbinding"></a>Совместное использование порта конечными точками службы и обмена метаданными при помощи NetTcpBinding  
 Если указать в качестве адреса базы службы net.tcp://MyServer:8080/MyService и добавить следующие конечные точки:  
  
```xml  
<services>  
  <service name="Microsoft.Samples.NetTcp.CalculatorService">  
    <endpoint address="calcsvc" binding ="netTcpBinding" contract="Microsoft.Samples.NetTcp.ICalculator"/>  
    <endpoint address="mex" binding="mexTcpBinding" contract="IMetadataExchange" />  
  </service>  
</services>  
```  
  
 А если модифицировать один из параметров NetTcpBinding, как показано в следующем фрагменте конфигурации:  
  
```xml  
<bindings>  
  <netTcpBinding>  
    <binding closeTimeout="00:01:00" openTimeout="00:01:00" receiveTimeout="00:10:00" sendTimeout="00:01:00" transactionFlow="false" transferMode="Buffered" transactionProtocol="OleTransactions" hostNameComparisonMode="StrongWildcard" listenBacklog="10" maxBufferPoolSize="524288" maxBufferSize="65536" maxConnections="11" maxReceivedMessageSize="65536">  
      <readerQuotas maxDepth="32" maxStringContentLength="8192" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384"/>  
      <reliableSession ordered="true" inactivityTimeout="00:10:00" enabled="false"/>  
      <security mode="Transport">  
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign"/>  
      </security>  
    </binding>  
  </netTcpBinding>  
</bindings>  
```  
  
 Появится следующая ошибка: необработанное исключение: System.ServiceModel.AddressAlreadyInUseException: уже есть прослушиватель на конечной точке IP 0.0.0.0:9000 можно обойти эту ошибку, указав полный URL-адрес с другим портом для конечной точки MEX, как показано в следующем фрагменте конфигурации:  
  
```xml
<services>  
  <service name="Microsoft.Samples.NetTcp.CalculatorService">  
    <endpoint address="calcsvc" binding ="netTcpBinding" contract="Microsoft.Samples.NetTcp.ICalculator"/>  
    <endpoint address="net.tcp://localhost:9001/servicemodelsamples/mex" binding="mexTcpBinding" contract="IMetadataExchange" />  
  </service>  
</services>  
```  
  
<a name="BK_MK99"></a>   
## <a name="when-calling-a-wcf-web-http-application-from-a-wcf-soap-application-the-service-returns-the-following-error-405-method-not-allowed"></a>При вызове веб-приложения HTTP WCF из приложения службы протокола SOAP WCF возвращается следующая ошибка: «405 Метод запрещен»  
 Вызов приложения WCF Web HTTP (службы, использующей <xref:System.ServiceModel.WebHttpBinding> и <xref:System.ServiceModel.Description.WebHttpBehavior>) из WCF служба может создать следующее исключение: `Unhandled Exception: System.ServiceModel.FaultException`1[System.ServiceModel.ExceptionDetail]: удаленный сервер вернул неожиданный ответ : (405) метод не разрешено. "это исключение возникает потому, что WCF перезаписывает исходящий <xref:System.ServiceModel.OperationContext> входящим <xref:System.ServiceModel.OperationContext>. Чтобы решить эту проблему, создайте <xref:System.ServiceModel.OperationContextScope> в операции веб-службы HTTP WCF. Пример:  
  
```csharp
public string Echo(string input)  
{  
    using (new OperationContextScope(this.InnerChannel))  
    {  
        return base.Channel.Echo(input);  
    }  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Отладка ошибок проверки подлинности Windows](../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)
