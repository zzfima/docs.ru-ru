---
title: Поведения безопасности в WCF
ms.date: 03/30/2017
ms.assetid: 513232c0-39fd-4409-bda6-5ebd5e0ea7b0
ms.openlocfilehash: f56bbd66aa61b8db9d6e720fb3a67ddbbf5e267e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184536"
---
# <a name="security-behaviors-in-wcf"></a>Поведения безопасности в WCF
В Фонде связи Windows (WCF) поведение изменяет поведение времени выполнения на уровне обслуживания или на уровне конечных точек. (Для получения дополнительной информации о поведении в целом [см.](../../../../docs/framework/wcf/specifying-service-run-time-behavior.md) *Поведение безопасности* позволяет контролировать журналы учетных данных, проверки подлинности, авторизации и аудита. Поведения можно использовать путем программирования или через конфигурацию. В этом разделе основное внимание уделяется настройке следующих поведений, связанных с функциями безопасности:  
  
- serviceCredentials>. [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)  
  
- clientCredentials>. [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)  
  
- сервисАвторизация>. [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)  
  
- serviceSecurityAudit>. [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md)  
  
- сервисMetadata>, который также позволяет указать безопасную конечную точку, к которой клиенты могут получить доступ для метаданных. [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md)  
  
## <a name="setting-credentials-with-behaviors"></a>Задание учетных данных с помощью поведений  
 Используйте [ \<службуCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) и [ \<>clientCredentials,](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) чтобы установить учетные данные для службы или клиента. Необходимость задания учетных данных определяется конфигурацией используемой привязки. Например, если задан режим безопасности `None`, ни клиенты, ни службы не проверяют подлинность друг друга и не требуют учетных данных какого-либо типа.  
  
 С другой стороны, привязка службы может требовать тип учетных данных клиента. В этом случае может потребоваться задать значение учетных данных с помощью поведения. (Для получения дополнительной информации о возможных типах учетных данных [см.](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md) В некоторых случаях, например, когда учетные данные Windows используются для проверки подлинности, среда автоматически устанавливает фактическое значение учетных данных, и вам не нужно явно устанавливать значение учетных данных (если вы не хотите указать другой набор учетных данных).  
  
 Все учетные данные службы находятся в качестве элементов детской [ \<службыBehaviors>. ](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) В следующем примере показан сертификат, используемый в качестве учетных данных службы.  
  
```xml  
<configuration>  
 <system.serviceModel>  
  <behaviors>  
   <serviceBehaviors>  
    <behavior name="ServiceBehavior1">  
     <serviceCredentials>  
      <serviceCertificate findValue="000000000000000000000000000"
                          storeLocation="CurrentUser"  
      storeName="Root" x509FindType="FindByThumbprint" />  
     </serviceCredentials>  
    </behavior>  
   </serviceBehaviors>  
  </behaviors>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="service-credentials"></a>Учетные данные службы  
 [ \<>serviceCredentials](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) содержит четыре элемента ребенка. Эти элементы и их применение рассматриваются в следующих подразделах.  
  
### <a name="servicecertificate-element"></a>\<serviceCertificate> Элемент  
 Этот элемент используется для задания сертификата X.509, который используется для проверки подлинности службы при подключении к клиентам в режиме безопасности сообщений. Если используется сертификат, который периодически обновляется, то его отпечаток изменяется. В этом случае следует использовать имя субъекта в виде `X509FindType`, поскольку сертификат может быть выдан повторно с тем же именем субъекта.  
  
 Для получения дополнительной [информации](../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)об использовании элемента см.  
  
### <a name="certificate-of-clientcertificate-element"></a>\<сертификат> \<клиентского сертификата> Элемента  
 Используйте [ \<сертификат>](../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md) элемент, когда служба должна иметь сертификат клиента заранее, чтобы безопасно общаться с клиентом. Это характерно для дуплексного обмена данными. В более распространенном варианте "запрос/ответ" клиент включает сертификат в запрос, который используется службой для обеспечения безопасности отклика, направляемого назад клиенту. Однако при дуплексном обмене данными запросы и ответы не используются. Служба не может логически вывести сертификат клиента из передаваемых данных, поэтому служба должна заранее получить сертификат клиента, чтобы обеспечить безопасность сообщений для клиента. Необходимо получить сертификат клиента при согласовании вне диапазона и указать сертификат с помощью этого элемента. Для получения дополнительной информации о дуплексных услугах [см.](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
  
### <a name="authentication-of-clientcertificate-element"></a>\<> аутентификации \<> элемента сертификата>  
 Элемент [ \<проверки подлинности>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) позволяет настроить способ проверки подлинности клиентов. Для атрибута `CertificateValidationMode` можно задать значение `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` или `Custom`. По умолчанию уровень `ChainTrust`устанавливается, который указывает, что каждый сертификат должен быть найден в иерархии сертификатов, заканчивающихся в *корневом органе* в верхней части цепочки. Это наиболее безопасный режим. Также можно установить значение `PeerOrChainTrust`, в этом случае будут приниматься как самостоятельно выдаваемые сертификаты (доверие одноранговой группы), так и сертификаты, которые находятся в цепи доверия. Данное значение используется при разработке и отладке клиентов и служб, так как самостоятельно выданные сертификаты не нужно приобретать у доверенного центра сертификации. При развертывании клиента вместо этого значения следует использовать значение `ChainTrust`. Также можно установить значение `Custom`. При установке значения `Custom` необходимо также задать атрибут `CustomCertificateValidatorType` для сборки и тип, который используется при проверке сертификата. Для создания собственного пользовательского модуля проверки необходимо наследование от абстрактного класса <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  
  
### <a name="issuedtokenauthentication-element"></a>\<выпущентокенАутентация> элемент  
 В сценарии с выданным маркером имеется три этапа. На первом этапе клиент, пытающийся получить доступ к службе, передается *на безопасную службу токенов* (STS). Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language (SAML). После этого клиент возвращается к службе с этим маркером. Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента. Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе. [ \<Элемент, выдаваемыйToкенAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) элемент, является репозиторием для любых таких безопасных сертификатов службы токенов. Чтобы добавить сертификаты, используйте [ \<известныеСертификаты>. ](../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md) Вставьте [ \<>для](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) каждого сертификата, как показано в следующем примере.  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"
           storeLocation="LocalMachine" storeName="My"
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 По умолчанию сертификаты должны быть получены от службы маркеров безопасности. Эти "известные" сертификаты гарантируют, что доступ к службе могут получить только допустимые клиенты.  
  
 Необходимо использовать [ \<разрешенную коллекцию>AudienceUris](../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md) в федеративном приложении, используюемом `SamlSecurityToken` *защищенную службу токенов* (STS), которая выдает маркеры безопасности. При выпуске маркера безопасности служба STS также может указать универсальный код ресурса (URI) веб-служб, для которых предназначен маркер безопасности, добавив выражение `SamlAudienceRestrictionCondition` к маркеру безопасности. Это позволяет коду `SamlSecurityTokenAuthenticator` для веб-службы получателя проверить, что выданный маркер безопасности предназначен для данной службы, указав на необходимость выполнения соответствующей проверки. Для этого выполните следующие действия.  
  
- Установите `audienceUriMode` атрибут [ \<выпускаемыхToкенПодлинной>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) `Always` или `BearerKeyOnly`.  
  
- Задайте набор допустимых универсальных кодов ресурса (URI), добавив их в данную коллекцию. Для этого вставьте [ \<>добавления](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md) для каждого URI  
  
 Дополнительные сведения см. в разделе <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.  
  
 Для получения дополнительной информации об использовании этого элемента конфигурации [см.](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
  
#### <a name="allowing-anonymous-cardspace-users"></a>Разрешение анонимных пользователей CardSpace  
 Если для атрибута `AllowUntrustedRsaIssuers` элемента `<IssuedTokenAuthentication>` явно задано значение `true`, любой клиент может представить самостоятельно выданный маркер, подписанный произвольной парой ключей RSA. Эмитенту *не доверяют,* поскольку ключ не имеет данных эмитента, связанных с ним. Пользователь CardSpace может создать карту, которая включает в себя самовыдаваемые заявления о личности. Эту возможность следует использовать с осторожностью. Используя эту функцию, считайте открытый ключ RSA просто более безопасным паролем, который должен храниться в базе данных вместе с именем пользователя. Прежде чем разрешить клиенту доступ к службе, проверьте представленный клиентом открытый ключ RSA, сравнив его с хранящимся открытым ключом для указанного имени пользователя. Это подразумевает, что организован процесс регистрации, в котором пользователи могут регистрировать свои имена пользователя и связывать их с самостоятельно изданными открытыми ключами RSA.  
  
## <a name="client-credentials"></a>Учетные данные клиента  
 Учетные данные клиента используются для проверки подлинности клиента при подключении к службам в случаях, когда требуется взаимная проверка подлинности. Данный раздел можно использовать для задания сертификатов служб для сценариев, где клиент должен обеспечить защиту сообщений, передаваемых службе, с помощью сертификатов службы.  
  
 В рамках сценария федерации также можно настроить в клиенте использование токенов, выданных службой токенов безопасности или локальным источником токенов. Для получения дополнительной информации о [Federation and Issued Tokens](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)федеративных сценариях см. Все учетные данные клиента находятся под [ \<конечными точкамиBehaviors>, ](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)как показано в следующем коде.  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="EndpointBehavior1">  
   <clientCredentials>  
    <clientCertificate findValue="cn=www.contoso.com"
        storeLocation="LocalMachine"  
        storeName="AuthRoot" x509FindType="FindBySubjectName" />  
    <serviceCertificate>  
     <defaultCertificate findValue="www.cohowinery.com"
                    storeLocation="LocalMachine"  
                    storeName="Root" x509FindType="FindByIssuerName" />  
    <authentication revocationMode="Online"  
                    trustedStoreLocation="LocalMachine" />  
    </serviceCertificate>  
   </clientCredentials>  
  </behavior>  
 </endpointBehaviors>  
```  
  
#### <a name="clientcertificate-element"></a>\<> элемент аттестата>  
 Задает сертификат, используемый для проверки подлинности клиента с помощью этого элемента. Для получения дополнительной [информации см.](../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)  
  
#### <a name="httpdigest"></a>\<httpDigest>  
 Эта функция должна быть включена с помощью Active Directory в Windows и службах IIS. Для получения дополнительной информации, см [Digest аутентификации в IIS 6.0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).  
  
#### <a name="issuedtoken-element"></a>\<выпущенныйтокен> Элемент  
 [ \<Выдаваемый>содержит](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) элементы, используемые для настройки локального эмитента токенов, или поведения, используемые с службой маркеров безопасности. Для получения инструкций по настройке клиента для использования локального эмитента [см.](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
  
#### <a name="localissueraddress"></a>\<местныйКакерАдрес>  
 Задает адрес службы маркеров безопасности по умолчанию. Это используется, <xref:System.ServiceModel.WSFederationHttpBinding> когда не указывается URL-адрес службы маркеров безопасности, или когда `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` адрес `null`эмитента федеративной привязки или . В этих случаях необходимо настроить объект <xref:System.ServiceModel.Description.ClientCredentials> с использованием адреса локального издателя и привязки, с помощью которой будет осуществляться взаимодействие с этим издателем.  
  
#### <a name="issuerchannelbehaviors"></a>\<issuerChannelBehaviors>  
 Используйте [ \<>,](../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md) что Определите поведение клиента в [ \<разделе endpointBehaviors>.](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) Чтобы использовать определенное поведение, `add` добавьте `<issuerChannelBehaviors>` элемент <> элемент с двумя атрибутами. Задайте в атрибуте `issuerAddress` URL-адрес службы маркеров безопасности, а в атрибуте `behaviorConfiguration` - имя определенного поведения конечной точки, как показано в следующем примере.  
  
```xml  
<clientCredentials>  
   <issuedToken>  
      <issuerChannelBehaviors>  
         <add issuerAddress="http://www.contoso.com"  
               behaviorConfiguration="clientBehavior1" />
```  
  
#### <a name="servicecertificate-element"></a>\<serviceCertificate> Элемент  
 Этот элемент служит для управления проверкой подлинности сертификатов службы.  
  
 Элемент [ \<сертификата по умолчанию>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md) может хранить один сертификат, используемый при отсутствии сертификата.  
  
 Используйте [ \<scopedCertificates>](../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md) и [ \<добавляйте>](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md) к установленным сертификатам обслуживания, которые связаны с конкретными службами. Элемент `<add>` содержит атрибут `targetUri`, который служит для связывания сертификата со службой.  
  
 Элемент [ \<проверки подлинности>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) определяет уровень доверия, используемый для проверки подлинности сертификатов. По умолчанию для уровня устанавливается значение ChainTrust, указывающее, что каждый сертификат должен находиться в иерархии сертификатов, которая на самом верху цепи завершается доверенным центром сертификации. Это наиболее безопасный режим. Также можно установить значение PeerOrChainTrust. В этом случае будут приниматься как самостоятельно выдаваемые сертификаты (доверие одноранговой группы), так и сертификаты, которые находятся в цепочке доверия. Данное значение используется при разработке и отладке клиентов и служб, так как самостоятельно выданные сертификаты не нужно приобретать у доверенного центра сертификации. При развертывании клиента вместо этого значения следует использовать значение "ChainTrust". Также можно задать значение "Custom" или "None". Чтобы использовать значение "Custom", необходимо также установить для атрибута `CustomCertificateValidatorType` значение сборки и типа, которые используются при проверке сертификата. Для создания собственного пользовательского модуля проверки необходимо наследование от абстрактного класса <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Для получения дополнительной информации [см. Как: Создать службу, которая использует пользовательский валидатор сертификата](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
 Элемент [ \<проверки подлинности>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) включает `RevocationMode` атрибут, который определяет, как сертификаты проверяются на отзыв. По умолчанию используется значение online, которое указывает, что проверка отзыва сертификата выполняется автоматически. Для получения дополнительной [информации см.](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
  
## <a name="serviceauthorization"></a>ServiceAuthorization  
 [ \<Элемент>службы Авторизация](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) содержит элементы, влияющие на авторизацию, пользовательские поставщики ролей и олицетворение.  
  
 Класс <xref:System.Security.Permissions.PrincipalPermissionAttribute> применяется к методу службы. Этот атрибут указывает группы пользователей, которые следует использовать при авторизации использования защищенного метода. Значение по умолчанию - "UseWindowsGroups". Оно указывает, что при попытке доступа к ресурсу поиск идентификации выполняется в таких группах Windows, как "Администраторы" или "Пользователи". Можно также указать "UseAspNetRoles" для использования пользовательского поставщика `system.web` ролей, настроенного под элементом <>, как показано в следующем коде.  
  
```xml  
<system.web>  
  <membership defaultProvider="SqlProvider"
   userIsOnlineTimeWindow="15">  
     <providers>  
       <clear />  
       <add
          name="SqlProvider"
          type="System.Web.Security.SqlMembershipProvider"
          connectionStringName="SqlConn"  
          applicationName="MembershipProvider"  
          enablePasswordRetrieval="false"  
          enablePasswordReset="false"  
          requiresQuestionAndAnswer="false"  
          requiresUniqueEmail="true"  
          passwordFormat="Hashed" />  
     </providers>  
   </membership>  
  <!-- Other configuration code not shown.-->  
</system.web>  
```  
  
 В следующем примере показано использование элемента `roleProviderName` с атрибутом `principalPermissionMode`.  
  
```xml  
<behaviors>  
 <behavior name="ServiceBehaviour">
  <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                        roleProviderName ="SqlProvider" />  
</behavior>
   <!-- Other configuration code not shown. -->  
</behaviors>  
```  
  
## <a name="configuring-security-audits"></a>Настройка аудита безопасности  
 Используйте [ \<сервисSecurityAudit>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) указать журнал, написанный, и какие типы событий для входа. Для получения дополнительной [информации см.](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
  
```xml  
<system.serviceModel>  
<serviceBehaviors>  
  <behavior name="NewBehavior">  
    <serviceSecurityAudit auditLogLocation="Application"
             suppressAuditFailure="true"  
             serviceAuthorizationAuditLevel="Success"
             messageAuthenticationAuditLevel="Success" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="secure-metadata-exchange"></a>Безопасный обмен метаданными  
 Экспорт метаданных в клиенты удобен для разработчиков служб и клиентов, так как позволяет загружать конфигурацию и код клиента. Для снижения подверженности службы действиям недобросовестных пользователей перенос можно защитить с помощью механизма SSL по протоколу HTTP (HTTPS). Для этого необходимо вначале выполнить привязку подходящего сертификата X.509 к конкретному порту компьютера, на котором размещена служба. (Для получения дополнительной [информации см. Работа с сертификатами.)](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) Во-вторых, добавьте [ \<>службыMetadata](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) в `true`конфигурацию службы и установите `HttpsGetEnabled` атрибут. После этого следует присвоить атрибуту `HttpsGetUrl` URL-адрес конечной точки метаданных службы, как показано в следующем примере.  
  
```xml  
<behaviors>  
 <serviceBehaviors>  
  <behavior name="NewBehavior">  
    <serviceMetadata httpsGetEnabled="true"
     httpsGetUrl="https://myComputerName/myEndpoint" />  
  </behavior>  
 </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Аудита](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)
- [Модель безопасности для Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
