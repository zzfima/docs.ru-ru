---
title: "Общие сведения о безопасности транспорта | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 00959326-aa9d-44d0-af61-54933d4adc7f
caps.latest.revision: 23
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 23
---
# Общие сведения о безопасности транспорта
Механизмы обеспечения безопасности транспорта в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] зависят от привязки и используемого транспорта. Например, при использовании <xref:System.ServiceModel.WSHttpBinding> класс, транспорт HTTP и основным механизмом обеспечения безопасности транспорта — Secure Sockets Layer (SSL) по протоколу HTTP, обычно называемый HTTPS. В данном разделе рассматриваются основные механизмы обеспечения безопасности транспорта, которые используются в привязках, предусмотренных в системе [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
> [!NOTE]
>  Если средства обеспечения безопасности на основе SSL используются с платформой .NET Framework версии 3.5 и более поздней версии, то для проверки цепочки сертификатов для сертификата службы клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует как промежуточные сертификаты в своем хранилище сертификатов, так и промежуточные сертификаты, полученные в процессе согласования SSL. Платформа .NET Framework 3.0 использует только промежуточные сертификаты, установленные в локальном хранилище сертификатов.  
  
> [!WARNING]
>  Если используется безопасность транспорта, <xref:System.Treading.Thread.CurrentPrincipal%2A> свойства могут быть перезаписаны. Чтобы избежать присвойте <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermission%2A> значение None. <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> поведение службы, которое можно задать в описании службы.  
  
## <a name="basichttpbinding"></a>BasicHttpBinding  
 По умолчанию <xref:System.ServiceModel.BasicHttpBinding> класс не обеспечивает безопасность. Эта привязка предназначена для взаимодействия с поставщиками веб-служб, которые не реализуют средства обеспечения безопасности. Тем не менее, можно переключиться на безопасность, установив <xref:System.ServiceModel.BasicHttpSecurity.Mode%2A> свойству любое значение, кроме <xref:System.ServiceModel.BasicHttpSecurityMode>. Чтобы включить режим безопасности транспорта, присвойте свойству значение <xref:System.ServiceModel.BasicHttpSecurityMode>.  
  
### <a name="interoperation-with-iis"></a>Взаимодействие с IIS  
 <xref:System.ServiceModel.BasicHttpBinding> класс в основном используется для взаимодействия с существующими веб-службами, и многие из этих служб размещаются Internet Information Services (IIS). Поэтому безопасность транспорта для этой привязки предназначена для беспрепятственного взаимодействия с узлами IIS. Это делается, установив режим безопасности <xref:System.ServiceModel.BasicHttpSecurityMode> и последующего задания типа учетных данных клиента. Значения типа учетных данных соответствуют механизмам безопасности каталогов IIS. В следующем коде показаны установка режима и задание в качестве типа учетных данных типа Windows. Эту конфигурацию можно использовать, когда клиент и сервер находятся в одном домене Windows.  
  
 [!code-csharp[c_ProgrammingSecurity#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#10)]
 <!-- TODO: review snippet reference [!code-vb[c_ProgrammingSecurity#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#10)]  -->  
  
 Или в виде конфигурации:  
  
```xml  
<bindings>  
  <basicHttpBinding>  
    <binding name="SecurityByTransport">  
      <security mode="Transport">  
        <transport clientCredentialType="Windows" />  
       </security>  
     </binding>  
  </basicHttpBinding>  
</bindings>  
```  
  
 В следующих разделах рассматриваются другие типы учетных данных клиентов.  
  
#### <a name="basic"></a>Basic  
 Соответствует методу обычной проверки подлинности в IIS. При использовании этого режима на сервере IIS должны быть настроены учетные записи пользователей Windows и соответствующие разрешения файловой системы NTFS. [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iis601](../../../../includes/iis601-md.md)], в разделе [Включение обычной проверки подлинности и настройка имени области](http://go.microsoft.com/fwlink/?LinkId=88592). [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iisver](../../../../includes/iisver-md.md)], в разделе [бета-версия IIS 7.0: Настройка обычной проверки подлинности](http://go.microsoft.com/fwlink/?LinkId=88593).  
  
#### <a name="certificate"></a>Сертификат  
 В IIS предусмотрена функция, требующая, чтобы клиенты входили в систему с использованием сертификата. Эта возможность также позволяет IIS сопоставить сертификат клиента с учетной записью Windows. [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iis601](../../../../includes/iis601-md.md)], в разделе [включение сертификатов клиентов в IIS 6.0](http://go.microsoft.com/fwlink/?LinkId=88594). [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iisver](../../../../includes/iisver-md.md)], в разделе [бета-версия IIS 7.0: Настройка сертификатов сервера в IIS 7.0](http://go.microsoft.com/fwlink/?LinkId=88595).  
  
#### <a name="digest"></a>Digest  
 Дайджест-проверка подлинности подобна обычной проверке подлинности, но имеет преимущество, заключающееся в передаче учетных данных в виде хэша, а не открытого текста. [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iis601](../../../../includes/iis601-md.md)], в разделе [дайджест-проверка подлинности в IIS 6.0](http://go.microsoft.com/fwlink/?LinkID=88443). [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iisver](../../../../includes/iisver-md.md)], в разделе [бета-версия IIS 7.0: Настройка дайджест-проверка подлинности](http://go.microsoft.com/fwlink/?LinkId=88596).  
  
#### <a name="windows"></a>Windows  
 Соответствует встроенной проверке подлинности Windows в IIS. При задании этого значения также предполагается, что сервер находится в домене Windows, в котором для взаимодействия с контроллером домена используется протокол Kerberos. Если сервер не находится в домене с поддержкой Kerberos или происходит сбой системы Kerberos, можно использовать значение NTLM, описанное в следующем разделе. [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iis601](../../../../includes/iis601-md.md)], в разделе [встроенная проверка подлинности Windows в службах IIS 6.0](http://go.microsoft.com/fwlink/?LinkId=88597). [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[iisver](../../../../includes/iisver-md.md)], в разделе [бета-версия IIS 7.0: Настройка сертификатов сервера в IIS 7.0](http://go.microsoft.com/fwlink/?LinkId=88595).  
  
#### <a name="ntlm"></a>NTLM  
 Это позволяет серверу использовать NTLM для проверки подлинности в случае сбоя протокола Kerberos. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Настройка сервера IIS в [!INCLUDE[iis601](../../../../includes/iis601-md.md)], в разделе [Принудительная проверка подлинности NTLM](http://go.microsoft.com/fwlink/?LinkId=88598). Для [!INCLUDE[iisver](../../../../includes/iisver-md.md)] проверка подлинности Windows включает проверку подлинности NTLM. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][IIS 7.0 Beta: Настройка сертификатов сервера в IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=88595).  
  
## <a name="wshttpbinding"></a>WsHttpBinding  
 <xref:System.ServiceModel.WSHttpBinding> класс предназначен для взаимодействия со службами, которые реализуют WS-* спецификации. Безопасность транспорта для этой привязки обеспечивается посредством протокола SSL по протоколам HTTP или HTTPS. Чтобы создать приложение [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], использующее SSL, для размещения этого приложения используйте IIS. В случае создания резидентного приложения используйте средство HttpCfg.exe для привязки сертификата X.509 к конкретному порту на компьютере. Номер порта указывается в качестве компонента приложения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] как адрес конечной точки. При использовании транспортного режима адрес конечной точки должен включать протокол HTTPS; в противном случае во время выполнения будет вызвано исключение. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Безопасность транспорта HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
 Проверка подлинности клиента, задайте <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> свойство <xref:System.ServiceModel.HttpTransportSecurity> одно из <xref:System.ServiceModel.HttpClientCredentialType> значений перечисления. Значения перечисления идентичны типам учетных данных клиента для <xref:System.ServiceModel.BasicHttpBinding> и предназначены для размещения со службами IIS.  
  
 В следующем примере показана привязка, используемая с учетными данными клиента типа Windows.  
  
 [!code-csharp[c_ProgrammingSecurity#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#11)]
 [!code-vb[c_ProgrammingSecurity#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#11)]  
  
## <a name="wsdualhttpbinding"></a>WSDualHttpBinding  
 Эта привязка обеспечивает безопасность только на уровне сообщений, а не на транспортном уровне.  
  
## <a name="nettcpbinding"></a>NetTcpBinding  
 <xref:System.ServiceModel.NetTcpBinding> класс использует протокол TCP для передачи сообщений. Безопасность транспортного режима обеспечивается реализацией протокола TLS по TCP. Реализация TLS обеспечивается операционной системой.  
  
 Можно также указать тип учетных данных клиента, задав <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> свойство <xref:System.ServiceModel.TcpTransportSecurity> одно из <xref:System.ServiceModel.TcpClientCredentialType> значения, как показано в следующем коде.  
  
 [!code-csharp[c_ProgrammingSecurity#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#12)]
 [!code-vb[c_ProgrammingSecurity#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#12)]  
  
#### <a name="client"></a>"Клиент";  
 На стороне клиента, необходимо указать сертификат с помощью <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> метод <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> класса.  
  
> [!NOTE]
>  В случае использования безопасности Windows сертификат не требуется.  
  
 В следующем коде используется отпечаток сертификата, который однозначно идентифицирует его. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]сертификаты, в разделе [работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
 [!code-csharp[c_ProgrammingSecurity#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#13)]
 [!code-vb[c_ProgrammingSecurity#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#13)]  
  
 Сертификат можно также задать в конфигурации клиента с помощью [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) элемент в разделе поведений.  
  
```xml  
<behaviors>  
  <behavior>  
   <clientCredentials>  
     <clientCertificate findValue= "101010101010101010101010101010000000000"   
      storeLocation="LocalMachine" storeName="My"   
      X509FindType="FindByThumbPrint"/>  
     </clientCertificate>  
   </clientCredentials>  
 </behavior>  
</behaviors>    
```  
  
## <a name="netnamedpipebinding"></a>NetNamedPipeBinding  
 <xref:System.ServiceModel.NetNamedPipeBinding> класс предназначен для эффективного взаимодействия внутри компьютера, т. е для процессов, выполняющихся на том же компьютере, несмотря на то, что именованные каналы могут быть созданы между двумя компьютерами в той же сети. Эта привязка обеспечивает безопасность только на транспортном уровне. При создании приложений с использованием данной привязки адреса конечных точек должны включать "net.pipe" в качестве протокола адреса конечной точки.  
  
## <a name="wsfederationhttpbinding"></a>WSFederationHttpBinding  
 При использовании безопасности транспорта эта привязка использует SSL через HTTP, известный как HTTPS с маркера (<xref:System.ServiceModel.WSFederationHttpSecurityMode>). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]федеративных приложениях см. в разделе [Федерация и выданные маркеры](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
## <a name="netpeertcpbinding"></a>NetPeerTcpBinding  
 <xref:System.ServiceModel.NetPeerTcpBinding> класс представляет защищенный транспорт, предназначенный для эффективного взаимодействия с использованием функции сети peer-to-peer. Как указано в имени класса и привязки, применяется протокол TCP. Если для режима безопасности задано значение Transport, данная привязка реализует протокол TLS по TCP. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]функция peer-to-peer разделе [сети Peer-to-Peer](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="msmqintegrationbinding-and-netmsmqbinding"></a>MsmqIntegrationBinding и NetMsmqBinding  
 Полное обсуждение транспорта безопасности с очередью сообщений (ранее называемой MSMQ), в разделе [защита сообщений с помощью обеспечения безопасности транспорта](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md).  
  
## <a name="see-also"></a>См. также  
 [Программирование безопасности WCF](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)