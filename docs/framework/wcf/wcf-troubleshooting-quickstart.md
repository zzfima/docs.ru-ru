---
title: Примеры устранения неполадок WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], troubleshooting
- Windows Communication Foundation [WCF], troubleshooting
ms.assetid: a9ea7a53-f31a-46eb-806e-898e465a4992
ms.openlocfilehash: f85d37fde19767d7fd1e3002776b4816666cc7e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183058"
---
# <a name="wcf-troubleshooting-quickstart"></a>Примеры устранения неполадок WCF
В этом разделе приведено несколько известных проблем, с которыми столкнулись пользователи при разработке клиентов и служб WCF. Если проблема, с которой столкнулись вы, отсутствует в этом списке, рекомендуется настроить трассировку для данной службы. При этом будет создан файл трассировки, который можно просмотреть с помощью средства просмотра файлов трассировки и получить подробные сведения об исключениях, которые могут возникать в службе. Дополнительные сведения о настройке трассировки см. в разделе [Configuring Tracing](./diagnostics/tracing/configuring-tracing.md). Дополнительные сведения о средстве просмотра файлов трассировки см. в разделе [Service Trace Viewer Tool (SvcTraceViewer.exe)](service-trace-viewer-tool-svctraceviewer-exe.md).  
  
1. [После установки Windows 7 и IIS при попытке перейти к службе WCF выдается следующее сообщение об ошибке: «Ошибка HTTP 404.3 - не найдено»](#bkmk_0)  
  
     Ошибка HTTP 404.3 - не найдено. Запрашиваемая страница не может быть выдана из-за конфигурации расширения. Если страница - скрипт, добавьте обработчик. Если файл должен загружаться, добавьте MIME-сопоставление. Подробное описание ошибки InformationModule StaticFileModule.  
  
2. [Иногда я получаю MessageSecurityException на второй запрос, если мой клиент простаивает на некоторое время после первого запроса. Что происходит?](#BKMK_q1)  
  
3. [Мой сервис начинает отказываться от новых клиентов после того, как около 10 клиентов взаимодействуют с ним. Что происходит?](#BKMK_q2)  
  
4. [Можно ли загружать конфигурацию службы из расположения, отличного от файла конфигурации приложения WCF?](#BKMK_q3)  
  
5. [Мой сервис и клиент отлично работают, но я не могу заставить их работать, когда клиент находится на другом компьютере? Что происходит?](#BKMK_q4)  
  
6. [Когда я бросаю\<исключение FaultException>, где тип является исключением, я всегда получаю общий тип FaultException на клиенте, а не общий тип. Что происходит?](#BKMK_q5)  
  
7. [Кажется, что односторонние операции и операции по ответу запроса возвращаются примерно с той же скоростью, когда ответ не содержит данных. Что происходит?](#BKMK_q6)  
  
8. [Я использую сертификат X.509 с моим сервисом, и я получаю System.Security.Cryptography.CryptographicException. Что происходит?](#BKMK_q77)  
  
9. [Я изменил первый параметр операции с верхнего регистра на нижний регистр; Теперь мой клиент бросает исключение. Что происходит?](#BKMK_q88)  
  
10. [Я использую один из моих инструментов трассировки, и я получаю EndpointNotFoundException. Что происходит?](#BKMK_q99)  
  
11. [При вызове веб-приложения HTTP WCF из приложения службы протокола SOAP WCF возвращается следующая ошибка: «405 Метод запрещен»](#BK_MK99)  
  
 [Какой базовый адрес? Как это связано с адресом конечных точек?](#BKMK_q10)  
  
<a name="bkmk_0"></a>
## <a name="after-installing-windows-7-and-iis-when-i-attempt-to-browse-to-a-wcf-service-i-get-the-following-error-message-http-error-4043--not-found"></a>После установки Windows 7 и IIS при попытке перейти к службе WCF выдается следующее сообщение об ошибке: «Ошибка HTTP 404.3 - не найдено»  
 Полное сообщение об ошибке:  
  
 Ошибка HTTP 404.3 - не найдено. Запрашиваемая страница не может быть выдана из-за конфигурации расширения. Если страница - скрипт, добавьте обработчик. Если файл должен загружаться, добавьте MIME-сопоставление. Подробное описание ошибки InformationModule StaticFileModule.  
  
 Это сообщение об ошибке происходит, когда "Windows Communication Foundation HTTP Activation" явно не установлена в панели управления. Чтобы установить это перейдите на панель управления, нажмите Программы в нижнем левом углу окна. Установите переключатель «Включение компонентов Windows». Разверните элемент Microsoft .NET Framework 3.5.1 и выберите «Активация Windows Communication Foundation по HTTP».  
  
<a name="BKMK_q1"></a>
## <a name="sometimes-i-receive-a-messagesecurityexception-on-the-second-request-if-my-client-is-idle-for-a-while-after-the-first-request-what-is-happening"></a>Иногда при втором запросе возникает исключение MessageSecurityException, если клиент бездействует некоторое время после первого запроса. Что происходит?  
 Сбой второго запроса может произойти по двум причинам: (1) истекло время ожидания сеанса или (2) перезапущен веб-сервер, на котором размещена служба. В первом случае сеанс действителен до тех пор, пока служба не выйдет из строя. Если служба не получает запрос от клиента в течение периода времени, указанного в привязке службы (),<xref:System.ServiceModel.Channels.Binding.ReceiveTimeout%2A>служба прекращает сеанс безопасности. Последующие сообщения клиента приводят к исключению <xref:System.ServiceModel.Security.MessageSecurityException>. Клиент должен повторно установить безопасный сеанс со службой, чтобы отправлять будущие сообщения, или использовать маркер контекста безопасности с отслеживанием состояния. Токены контекста безопасности с отслеживанием состояния также позволяют защитить сеанс во время перезапуска веб-сервера. Для получения дополнительной информации об использовании маркеров безопасного контекста состояния в безопасном сеансе [см.](./feature-details/how-to-create-a-security-context-token-for-a-secure-session.md) Кроме того, можно отключить безопасные сеансы. При использовании [ \<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) связывания `establishSecurityContext` можно `false` настроить свойство для отсутсвия безопасных сеансов. Чтобы отключить безопасные сеансы для других привязок, необходимо создать пользовательскую привязку. Подробные сведения о создании пользовательской привязки см. в разделе [How to: Create a Custom Binding Using the SecurityBindingElement](./feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md). Перед применением этих параметров необходимо разобраться с требованиями безопасности приложения.  
  
<a name="BKMK_q2"></a>
## <a name="my-service-starts-to-reject-new-clients-after-about-10-clients-are-interacting-with-it-what-is-happening"></a>Когда со службой взаимодействует около 10 клиентов, она отклоняет подключение новых клиентов. Что происходит?  
 По умолчанию службы поддерживают не более 10 параллельных сеансов. Поэтому при использовании в привязках службы сеансов, служба принимает подключения новых клиентов до достижения этого числа. После этого служба отклоняет подключения новых клиентов, пока не будет закрыт один из текущих сеансов. Поддержку большего количества клиентов можно обеспечить несколькими способами. Если для службы не требуются сеансы, не используйте сеансовую привязку. (Для получения дополнительной [информации см.](using-sessions.md) Другим вариантом является увеличение лимита сеанса <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A> путем изменения значения свойства на число, соответствующее вашим обстоятельствам.  
  
<a name="BKMK_q3"></a>
## <a name="can-i-load-my-service-configuration-from-somewhere-other-than-the-wcf-applications-configuration-file"></a>Можно ли загружать конфигурацию службы из расположения, отличного от файла конфигурации приложения WCF?  
 Да, но необходимо создать пользовательский класс <xref:System.ServiceModel.ServiceHost> , переопределяющий метод <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> . Внутри этого метода можно вызвать базовый класс, чтобы сначала загрузить конфигурацию (если дополнительно требуется загрузить сведения о стандартной конфигурации), но можно также полностью заменить систему загрузки конфигурации. Если требуется загрузить конфигурацию из файла конфигурации, который отличается от файла конфигурации приложения, необходимо разобрать файл конфигурации самостоятельно и загрузить конфигурацию.  
  
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
  
- Возможно, потребуется использовать для адреса конечной точки клиента имя узла, а не "localhost".  
  
- Возможно, для приложения потребуется открыть порт. Дополнительные сведения см. в разделе [Firewall Instructions](./samples/firewall-instructions.md) примеров SDK.  
  
- Для других возможных проблем смотрите тему примеров [Запуск образцов Windows Communication Foundation Образцы](./samples/running-the-samples.md).  
  
- Если в клиенте используются учетные данные Windows и создается исключение <xref:System.ServiceModel.Security.SecurityNegotiationException>, настройте Kerberos, как указано ниже.  
  
    1. Добавьте учетные данные идентификации в элемент конечной точки в файле конфигурации клиента App.config.  
  
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
  
    2. Для этого запустите службу от имени учетной записи System или NetworkService. Чтобы создать командное окно в учетной записи System, выполните следующую команду.  
  
        ```console
        at 12:36 /interactive "cmd.exe"  
        ```  
  
    3. Разместите службу в службах IIS, которые по умолчанию используют учетную запись имени участника службы (SPN).  
  
    4. Зарегистрируйте в домене новое имя участника службы (SPN) с помощью программы SetSPN. Для этого необходимо быть администратором домена.  
  
 Для получения дополнительной информации о [Security Concepts Used in WCF](./feature-details/security-concepts-used-in-wcf.md) протоколе Kerberos см.  
  
- [Отладка ошибок проверки подлинности Windows](./feature-details/debugging-windows-authentication-errors.md)  
  
- [Регистрация имен субъектов-служб Kerberos в файле Http.sys](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms178119(v=sql.105))  
  
- [Сведения о Kerberos](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/bb742516(v%3dtechnet.10))  
  
<a name="BKMK_q5"></a>
## <a name="when-i-throw-a-faultexceptionexception-where-the-type-is-an-exception-i-always-receive-a-general-faultexception-type-on-the-client-and-not-the-generic-type-whats-happening"></a>Когда я бросаю\<исключение FaultException>, где тип является исключением, я всегда получаю общий тип FaultException на клиенте, а не общий тип. В чем причина?  
 Настоятельно рекомендуется создать свой собственный пользовательский тип данных об ошибке и объявить его в качестве типа сведений в контракте сбоя. Это необходимо, так как при использовании типов исключений, предоставляемых системой, могут возникнуть следующие проблемы.  
  
- Создается зависимость типов, которая не дает возможности воспользоваться одним из главных преимуществ приложений, ориентированных на службы.  
  
- Не удается воспользоваться стандартной сериализацией исключений. Некоторые из них, например <xref:System.Security.SecurityException>, могут вообще не сериализоваться.  
  
- Внутренние сведения сериализации доступны для клиентов. Для получения дополнительной информации [см.](specifying-and-handling-faults-in-contracts-and-services.md)  
  
 Однако при отладке приложения можно сериализовать сведения об исключении и возвратить их клиенту с помощью класса <xref:System.ServiceModel.Description.ServiceDebugBehavior> .  
  
<a name="BKMK_q6"></a>
## <a name="it-seems-like-one-way-and-request-reply-operations-return-at-roughly-the-same-speed-when-the-reply-contains-no-data-whats-happening"></a>Создается впечатление, что односторонние операции, а также операции запроса-ответа возвращаются примерно с той же скоростью, что и ответы без данных. В чем причина?  
 Если указывается, что операция является односторонней, это лишь означает, что контракт операции принимает входящее сообщение и не возвращает выходное сообщение. В WCF все вызовы клиента возвращаются, когда исходящие данные были записаны на провод или выбрасывается исключение. Односторонние операции выполняются таким же образом, и они могут создавать исключение, если не удается обнаружить службу, или заблокировать выполнение, если служба не готова к приему данных из сети. Как правило, в WCF это приводит к тому, что односторонние вызовы возвращаются клиенту быстрее, чем ответ запроса; но любое условие, замедлит отправку исходящих данных по сети, замедляет односторонние операции, а также операции по ответу запроса. Для получения дополнительной информации [Accessing Services Using a WCF Client](./feature-details/accessing-services-using-a-client.md)см. [One-Way Services](./feature-details/one-way-services.md)  
  
<a name="BKMK_q77"></a>
## <a name="im-using-an-x509-certificate-with-my-service-and-i-get-a-systemsecuritycryptographycryptographicexception-whats-happening"></a>В службе используется сертификат X.509, при этом получается исключение System.Security.Cryptography.CryptographicException. В чем причина?  
 Обычно это происходит после изменения учетной записи пользователя, в которой выполняется рабочий процесс IIS. Например, в Windows XP, если вы измените учетную запись пользователя по умолчанию, которую Aspnet_wp.exe выполняется с ASPNET на пользовательскую учетную запись пользователя, вы можете увидеть эту ошибку. Если используется закрытый ключ, его процесс должен иметь разрешение для доступа к файлу с этим ключом.  
  
 В этом случае необходимо предоставить учетной записи процесса права доступа для чтения файла с закрытым ключом. Например, если рабочий процесс IIS выполняется в учетной записи Бориса, ему необходимо предоставить права доступа для чтения файла, содержащего закрытый ключ.  
  
 Для получения дополнительной информации о том, как дать правильный доступ к учетной записи пользователя к файлу, который содержит закрытый ключ для конкретного сертификата X.509, [см.](./feature-details/how-to-make-x-509-certificates-accessible-to-wcf.md)  
  
<a name="BKMK_q88"></a>
## <a name="i-changed-the-first-parameter-of-an-operation-from-uppercase-to-lowercase-now-my-client-throws-an-exception-whats-happening"></a>В имени первого параметра операции прописные буквы были заменены на строчные, и теперь в клиенте выдается исключение. В чем причина?  
 Значения имен параметров в подписи операции являются частью договора и чувствительны к случаям. Используйте атрибут <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType> , чтобы различать имя локального параметра и метаданные, описывающие операцию для клиентских приложений.  
  
<a name="BKMK_q99"></a>
## <a name="im-using-one-of-my-tracing-tools-and-i-get-an-endpointnotfoundexception-whats-happening"></a>При использовании одного из средств трассировки получено исключение EndpointNotFoundException. В чем причина?  
 Если вы используете инструмент отслеживания, который не является системным механизмом <xref:System.ServiceModel.EndpointNotFoundException> отслеживания WCF, и вы получаете, <xref:System.ServiceModel.Description.ClientViaBehavior> что указывает на несоответствие фильтра адреса, вам нужно использовать класс, чтобы направить сообщения в утилиту отслеживания и иметь утилиту перенаправить эти сообщения на адрес службы. Класс <xref:System.ServiceModel.Description.ClientViaBehavior> изменяет заголовок адресации `Via` , чтобы задать следующий сетевой адрес отдельно от конечного получателя, указанного заголовком адресации `To` . Однако при этом не следует изменять адрес конечной точки, используемый для установки значения `To` .  
  
 В следующем примере кода показан пример файла конфигурации клиента.  
  
```xml
<endpoint
  address="http://localhost:8000/MyServer/"  
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
 Базовый адрес - это корневой адрес для класса <xref:System.ServiceModel.ServiceHost> . По умолчанию, если в конфигурацию службы добавлен класс <xref:System.ServiceModel.Description.ServiceMetadataBehavior> , язык описания веб-служб (WSDL) для всех конечных точек, публикуемых узлом, извлекается из базового HTTP-адреса, относительного адреса, предоставленного поведением метаданных, а также "?wsdl". Если вы знакомы с ASP.NET и IIS, базовый адрес эквивалентен виртуальному каталогу.  
  
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
  
 Появится следующее сообщение об ошибке: Необработанное исключение: System.ServiceModel. AddressAlreadyInUseException. Уже есть прослушиватель на конечной точке IP 0.0.0.0:9000. Можно обойти эту ошибку, указав полный URL-адрес с другим портом для конечной точки MEX, как показано в следующем фрагменте конфигурации:  
  
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
 Вызов приложения WCF Web HTTP (услуга, <xref:System.ServiceModel.WebHttpBinding> использующую и) <xref:System.ServiceModel.Description.WebHttpBehavior>из службы ``Unhandled Exception: System.ServiceModel.FaultException`1[System.ServiceModel.ExceptionDetail]: The remote server returned an unexpected response: (405) Method Not Allowed.`` WCF может генерировать следующее исключение: Это исключение происходит потому, что WCF перезаписывает исходящие <xref:System.ServiceModel.OperationContext> с входящими. <xref:System.ServiceModel.OperationContext> Чтобы решить эту проблему, создайте <xref:System.ServiceModel.OperationContextScope> в рамках операции службы WCF Web HTTP. Пример:  
  
```csharp
public string Echo(string input)  
{  
    using (new OperationContextScope(this.InnerChannel))  
    {  
        return base.Channel.Echo(input);  
    }  
}  
```  
  
## <a name="see-also"></a>См. также раздел

- [Отладка ошибок проверки подлинности Windows](./feature-details/debugging-windows-authentication-errors.md)
