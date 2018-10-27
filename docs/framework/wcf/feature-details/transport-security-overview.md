---
title: Общие сведения о безопасности транспорта
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 00959326-aa9d-44d0-af61-54933d4adc7f
ms.openlocfilehash: 44f0763aa09b2a9d036d13c9995d7ea978908d4c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188096"
---
# <a name="transport-security-overview"></a>Общие сведения о безопасности транспорта
Механизмы обеспечения безопасности транспорта в Windows Communication Foundation (WCF) зависят от привязки и используемого транспорта. Например, при использовании класса <xref:System.ServiceModel.WSHttpBinding> транспортом является протокол HTTP и в качестве основного механизма защиты транспорта применяется протокол SSL через HTTP, обычно называемый HTTPS. В этом разделе рассматриваются основные транспорта механизмы безопасности, используемые в привязках, предоставляемых системой WCF.  
  
> [!NOTE]
>  При использовании безопасности SSL с .NET Framework 3.5 и более поздних версиях клиент WCF использует промежуточные сертификаты в своем хранилище сертификатов, и промежуточные сертификаты, полученные в процессе согласования SSL для проверки цепочки сертификатов для службы сертификат. Платформа .NET Framework 3.0 использует только промежуточные сертификаты, установленные в локальном хранилище сертификатов.  
  
> [!WARNING]
>  При использовании системы безопасности транспорта свойство <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> не применяется. Чтобы избежать этого, присвойте свойству <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A?displayProperty=nameWithType> для <xref:System.ServiceModel.Description.PrincipalPermissionMode.None?displayProperty=nameWithType>. <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> - это поведение службы, которое можно задать в описании службы.  
  
## <a name="basichttpbinding"></a>BasicHttpBinding  
 По умолчанию класс <xref:System.ServiceModel.BasicHttpBinding> не обеспечивает безопасность. Эта привязка предназначена для взаимодействия с поставщиками веб-служб, которые не реализуют средства обеспечения безопасности. Однако режим безопасности можно включить, присвоив свойству <xref:System.ServiceModel.BasicHttpSecurity.Mode%2A> любое значение, кроме <xref:System.ServiceModel.BasicHttpSecurityMode.None>. Чтобы включить режим безопасности транспорта, присвойте этому свойству значение <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>.  
  
### <a name="interoperation-with-iis"></a>Взаимодействие с IIS  
 Класс <xref:System.ServiceModel.BasicHttpBinding> используется в основном для взаимодействия с существующими веб-службами, многие из которых размещаются в службах IIS. Поэтому безопасность транспорта для этой привязки предназначена для беспрепятственного взаимодействия с узлами IIS. Она обеспечивается посредством установки для режима безопасности значения <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> и последующего задания типа учетных данных клиента. Значения типа учетных данных соответствуют механизмам безопасности каталогов IIS. В следующем коде показаны установка режима и задание в качестве типа учетных данных типа Windows. Эту конфигурацию можно использовать, когда клиент и сервер находятся в одном домене Windows.  
  
 [!code-csharp[c_ProgrammingSecurity#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#10)] 
 [!code-vb[c_ProgrammingSecurity#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#10)]  
  
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
 Соответствует методу обычной проверки подлинности в IIS. При использовании этого режима на сервере IIS должны быть настроены учетные записи пользователей Windows и соответствующие разрешения файловой системы NTFS. Дополнительные сведения о [!INCLUDE[iis601](../../../../includes/iis601-md.md)], см. в разделе [Включение обычной проверки подлинности и настройка имени области](https://go.microsoft.com/fwlink/?LinkId=88592). Дополнительные сведения о [!INCLUDE[iisver](../../../../includes/iisver-md.md)], см. в разделе [бета-версия IIS 7.0: Настройка обычной проверки подлинности](https://go.microsoft.com/fwlink/?LinkId=88593).  
  
#### <a name="certificate"></a>Сертификат  
 В IIS предусмотрена функция, требующая, чтобы клиенты входили в систему с использованием сертификата. Эта возможность также позволяет IIS сопоставить сертификат клиента с учетной записью Windows. Дополнительные сведения о [!INCLUDE[iis601](../../../../includes/iis601-md.md)], см. в разделе [включение сертификатов клиентов в IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88594). Дополнительные сведения о [!INCLUDE[iisver](../../../../includes/iisver-md.md)], см. в разделе [бета-версия IIS 7.0: Настройка сертификатов сервера в IIS 7.0](https://go.microsoft.com/fwlink/?LinkId=88595).  
  
#### <a name="digest"></a>Digest  
 Дайджест-проверка подлинности подобна обычной проверке подлинности, но имеет преимущество, заключающееся в передаче учетных данных в виде хэша, а не открытого текста. Дополнительные сведения о [!INCLUDE[iis601](../../../../includes/iis601-md.md)], см. в разделе [дайджест-проверка подлинности в IIS 6.0](https://go.microsoft.com/fwlink/?LinkID=88443). Дополнительные сведения о [!INCLUDE[iisver](../../../../includes/iisver-md.md)], см. в разделе [бета-версия IIS 7.0: Настройка дайджест-проверка подлинности](https://go.microsoft.com/fwlink/?LinkId=88596).  
  
#### <a name="windows"></a>Windows  
 Соответствует встроенной проверке подлинности Windows в IIS. При задании этого значения также предполагается, что сервер находится в домене Windows, в котором для взаимодействия с контроллером домена используется протокол Kerberos. Если сервер не находится в домене с поддержкой Kerberos или происходит сбой системы Kerberos, можно использовать значение NTLM, описанное в следующем разделе. Дополнительные сведения о [!INCLUDE[iis601](../../../../includes/iis601-md.md)], см. в разделе [встроенная проверка подлинности Windows в IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88597). Дополнительные сведения о [!INCLUDE[iisver](../../../../includes/iisver-md.md)], см. в разделе [бета-версия IIS 7.0: Настройка сертификатов сервера в IIS 7.0](https://go.microsoft.com/fwlink/?LinkId=88595).  
  
#### <a name="ntlm"></a>NTLM  
 Это позволяет серверу использовать NTLM для проверки подлинности в случае сбоя протокола Kerberos. Дополнительные сведения о настройке IIS в [!INCLUDE[iis601](../../../../includes/iis601-md.md)], см. в разделе [Принудительная проверка подлинности NTLM](https://go.microsoft.com/fwlink/?LinkId=88598). Для [!INCLUDE[iisver](../../../../includes/iisver-md.md)] проверка подлинности Windows включает проверку подлинности NTLM. Дополнительные сведения см. в разделе [бета-версия IIS 7.0: Настройка сертификатов сервера в IIS 7.0](https://go.microsoft.com/fwlink/?LinkID=88595).  
  
## <a name="wshttpbinding"></a>WsHttpBinding  
 Класс <xref:System.ServiceModel.WSHttpBinding> предназначен для взаимодействия со службами, реализующими спецификации WS-*. Безопасность транспорта для этой привязки обеспечивается посредством протокола SSL по протоколам HTTP или HTTPS. Чтобы создать приложение WCF, использующее SSL, используйте IIS для размещения приложения. В случае создания резидентного приложения используйте средство HttpCfg.exe для привязки сертификата X.509 к конкретному порту на компьютере. Номер порта указывается как часть приложения WCF, как адрес конечной точки. При использовании транспортного режима адрес конечной точки должен включать протокол HTTPS; в противном случае во время выполнения будет вызвано исключение. Дополнительные сведения см. в разделе [безопасности транспорта HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
 Для проверки подлинности клиента присвойте свойству <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> класса <xref:System.ServiceModel.HttpTransportSecurity> одно из значений перечисления <xref:System.ServiceModel.HttpClientCredentialType>. Значения перечисления идентичны типам учетных данных клиентов для класса <xref:System.ServiceModel.BasicHttpBinding> и должны размещаться службами IIS.  
  
 В следующем примере показана привязка, используемая с учетными данными клиента типа Windows.  
  
 [!code-csharp[c_ProgrammingSecurity#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#11)]
 [!code-vb[c_ProgrammingSecurity#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#11)]  
  
## <a name="wsdualhttpbinding"></a>WSDualHttpBinding  
 Эта привязка обеспечивает безопасность только на уровне сообщений, а не на транспортном уровне.  
  
## <a name="nettcpbinding"></a>NetTcpBinding  
 Для передачи сообщений класс <xref:System.ServiceModel.NetTcpBinding> использует протокол TCP. Безопасность транспортного режима обеспечивается реализацией протокола TLS по TCP. Реализация TLS обеспечивается операционной системой.  
  
 Тип учетных данных клиента можно также задать, присвоив свойству <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> класса <xref:System.ServiceModel.TcpTransportSecurity> одно из значений <xref:System.ServiceModel.TcpClientCredentialType>, как показано в следующем коде.  
  
 [!code-csharp[c_ProgrammingSecurity#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#12)]
 [!code-vb[c_ProgrammingSecurity#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#12)]  
  
#### <a name="client"></a>"Клиент";  
 На клиенте следует задать сертификат с помощью метода <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> класса <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.  
  
> [!NOTE]
>  В случае использования безопасности Windows сертификат не требуется.  
  
 В следующем коде используется отпечаток сертификата, который однозначно идентифицирует его. Дополнительные сведения см. в разделе [Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
 [!code-csharp[c_ProgrammingSecurity#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#13)]
 [!code-vb[c_ProgrammingSecurity#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#13)]  
  
 Кроме того, укажите сертификат в конфигурации клиента с помощью [ \<clientCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) элемент в разделе поведений.  
  
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
 Класс <xref:System.ServiceModel.NetNamedPipeBinding> предназначен для эффективного взаимодействия внутри компьютера, т. е. для процессов, выполняющихся на одном компьютере, хотя между двумя компьютерами, расположенными в одной сети, могут быть созданы именованные каналы. Эта привязка обеспечивает безопасность только на транспортном уровне. При создании приложений с использованием данной привязки адреса конечных точек должны включать "net.pipe" в качестве протокола адреса конечной точки.  
  
## <a name="wsfederationhttpbinding"></a>WSFederationHttpBinding  
 При использовании безопасности транспорта эта привязка использует протокол SSL по HTTP, известный как HTTPS-протокол с выданным токеном (<xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential>). Дополнительные сведения о федеративных приложениях см. в разделе [Федерация и выданные маркеры](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
## <a name="netpeertcpbinding"></a>NetPeerTcpBinding  
 Класс <xref:System.ServiceModel.NetPeerTcpBinding> представляет защищенный транспорт, предназначенный для эффективного взаимодействия с использованием функции одноранговой сети. Как указано в имени класса и привязки, применяется протокол TCP. Если для режима безопасности задано значение Transport, данная привязка реализует протокол TLS по TCP. Дополнительные сведения о функции peer-to-peer см. в разделе [сети Peer-to-Peer](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="msmqintegrationbinding-and-netmsmqbinding"></a>MsmqIntegrationBinding и NetMsmqBinding  
 Подробное обсуждение транспорта безопасности с очередью сообщений (ранее называемой MSMQ), см. в разделе [защита безопасность транспорта с помощью сообщений](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md).  
  
## <a name="see-also"></a>См. также  
 [Программирование безопасности WCF](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
