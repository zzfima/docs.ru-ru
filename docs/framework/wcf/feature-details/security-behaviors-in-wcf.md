---
title: "Поведения безопасности в WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 513232c0-39fd-4409-bda6-5ebd5e0ea7b0
caps.latest.revision: 23
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 23
---
# Поведения безопасности в WCF
В [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] поведения изменяют порядок работы во время выполнения на уровне службы или на уровне конечной точки.\([!INCLUDE[crabout](../../../../includes/crabout-md.md)] о поведениях в целом см. в разделе [Указание поведения службы во время выполнения](../../../../docs/framework/wcf/specifying-service-run-time-behavior.md).\) *Поведения безопасности* позволяют управлять учетными данными, проверкой подлинности, авторизацией и журналами аудита.Поведения можно использовать путем программирования или через конфигурацию.В этом разделе основное внимание уделяется настройке следующих поведений, связанных с функциями безопасности:  
  
-   [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).  
  
-   [\<clientCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).  
  
-   [\<serviceAuthorization\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md).  
  
-   [\<serviceSecurityAudit\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md).  
  
-   Элемент [\<serviceMetadata\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md), также позволяющий указывать защищенную конечную точку, к которой клиенты могут обращаться за метаданными.  
  
## Задание учетных данных с помощью поведений  
 Чтобы задать значения учетных данных для службы или клиента, используйте элементы [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) и [\<clientCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).Необходимость задания учетных данных определяется конфигурацией используемой привязки.Например, если задан режим безопасности `None`, ни клиенты, ни службы не проверяют подлинность друг друга и не требуют учетных данных какого\-либо типа.  
  
 С другой стороны, привязка службы может требовать тип учетных данных клиента.В этом случае может потребоваться задать значение учетных данных с помощью поведения.\([!INCLUDE[crabout](../../../../includes/crabout-md.md)] о возможных типах учетных данных см. в разделе [Выбор типа учетных данных](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md).\) В некоторых случаях \(например, если для проверки подлинности используются учетные данные Windows\), среда автоматически устанавливает фактическое значение учетных данных, и не нужно явно задавать это значение \(кроме случая, когда требуется указать другой набор учетных данных\).  
  
 Все учетные данные службы находятся в дочерних элементах раздела [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md).В следующем примере показан сертификат, используемый в качестве учетных данных службы.  
  
```  
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
  
## Учетные данные службы  
 Элемент [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) содержит четыре дочерних элемента.Эти элементы и их применение рассматриваются в следующих подразделах.  
  
### Элемент \<serviceCertificate\>  
 Этот элемент используется для задания сертификата X.509, который используется для проверки подлинности службы при подключении к клиентам в режиме безопасности сообщений.Если используется сертификат, который периодически обновляется, то его отпечаток изменяется.В этом случае следует использовать имя субъекта в виде `X509FindType`, поскольку сертификат может быть выдан повторно с тем же именем субъекта.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] об использовании элемента см. в разделе [Практическое руководство. Задание значений учетных данных клиента](../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
### \<certificate\> элемента \<clientCertificate\>  
 Элемент [\<certificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md) используется в случаях, когда служба должна заранее получить сертификат клиента для безопасного обмена данными с клиентом.Это характерно для дуплексного обмена данными.В более распространенном варианте "запрос\/ответ" клиент включает сертификат в запрос, который используется службой для обеспечения безопасности отклика, направляемого назад клиенту.Однако при дуплексном обмене данными запросы и ответы не используются.Служба не может логически вывести сертификат клиента из передаваемых данных, поэтому служба должна заранее получить сертификат клиента, чтобы обеспечить безопасность сообщений для клиента.Вы должны получить сертификат клиента отдельным образом и указать данный сертификат с помощью этого элемента.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] дуплексных службах см. в разделе [Как создавать дуплексный контракт](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
### \<authentication\> элемента \<clientCertificate\>  
 Элемент [\<authentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) позволяет настраивать способ проверки подлинности клиентов.Для атрибута `CertificateValidationMode` можно задать значение `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` или `Custom`.По умолчанию установлен уровень `ChainTrust`, который определяет, что каждый сертификат должен находиться в иерархии сертификатов, заканчивающейся *корневым центром* на вершине цепи.Это наиболее безопасный режим.Также можно установить значение `PeerOrChainTrust`, в этом случае будут приниматься как самостоятельно выдаваемые сертификаты \(доверие одноранговой группы\), так и сертификаты, которые находятся в цепи доверия.Данное значение используется при разработке и отладке клиентов и служб, так как самостоятельно выданные сертификаты не нужно приобретать у доверенного центра сертификации.При развертывании клиента вместо этого значения следует использовать значение `ChainTrust`.Также можно установить значение `Custom`.При установке значения `Custom` необходимо также задать атрибут `CustomCertificateValidatorType` для сборки и тип, который используется при проверке сертификата.Для создания собственного пользовательского модуля проверки необходимо наследование от абстрактного класса <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  
  
### Элемент \<issuedTokenAuthentication\>  
 В сценарии с выданным маркером имеется три этапа.На первом этапе клиент, который пытается получить доступ к службе, направляется к *службе маркеров безопасности* \(STS\).Затем служба маркеров безопасности проводит проверку подлинности клиента и выдает клиенту маркер, обычно на языке Security Assertions Markup Language \(SAML\).После этого клиент возвращается к службе с этим маркером.Служба проверяет наличие в маркере данных, позволяющих проверить подлинность маркера и, соответственно, самого клиента.Для проверки подлинности маркера сертификат, используемый службой маркеров безопасности, должен быть известен службе.Элемент [\<issuedTokenAuthentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) является хранилищем подобных сертификатов службы маркеров безопасности.Используйте элемент [\<knownCertificates\>](../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md), чтобы добавить сертификаты.Вставьте элемент [\<добавление;\>](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) для каждого сертификата, как показано в следующем примере.  
  
```  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 По умолчанию сертификаты должны быть получены от службы маркеров безопасности.Эти "известные" сертификаты гарантируют, что доступ к службе могут получить только допустимые клиенты.  
  
 Коллекцию [\<allowedAudienceUris\>](../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md) следует использовать в федеративном приложении, которое использует *службу маркеров безопасности* \(STS\), выдающую маркеры безопасности `SamlSecurityToken`.При выпуске маркера безопасности служба STS также может указать универсальный код ресурса \(URI\) веб\-служб, для которых предназначен маркер безопасности, добавив выражение `SamlAudienceRestrictionCondition` к маркеру безопасности.Это позволяет коду `SamlSecurityTokenAuthenticator` для веб\-службы получателя проверить, что выданный маркер безопасности предназначен для данной службы, указав на необходимость выполнения соответствующей проверки. Для этого выполните следующие действия.  
  
-   Присвойте атрибуту `audienceUriMode` элемента [\<issuedTokenAuthentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) значение `Always` или `BearerKeyOnly`.  
  
-   Задайте набор допустимых URI, добавив их в эту коллекцию.Для этого вставьте элемент [\<добавление;\>](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md) для каждого универсального кода ресурса \(URI\).  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] об использовании этого элемента конфигурации см. в разделе [Как настраивать учетные данные службы федерации](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  
  
#### Разрешение анонимных пользователей CardSpace  
 Если для атрибута `AllowUntrustedRsaIssuers` элемента `<IssuedTokenAuthentication>` явно задано значение `true`, любой клиент может представить самостоятельно выданный маркер, подписанный произвольной парой ключей RSA.Этот издатель является *ненадежным*, так как с ключом не связаны никакие данные издателя.Пользователь [!INCLUDE[infocard](../../../../includes/infocard-md.md)] может создать самостоятельно изданную карту, содержащую самостоятельно предоставленные утверждения идентификации.Эту возможность следует использовать с осторожностью.Используя эту функцию, считайте открытый ключ RSA просто более безопасным паролем, который должен храниться в базе данных вместе с именем пользователя.Прежде чем разрешить клиенту доступ к службе, проверьте представленный клиентом открытый ключ RSA, сравнив его с хранящимся открытым ключом для указанного имени пользователя.Это подразумевает, что организован процесс регистрации, в котором пользователи могут регистрировать свои имена пользователя и связывать их с самостоятельно изданными открытыми ключами RSA.  
  
## Учетные данные клиента  
 Учетные данные клиента используются для проверки подлинности клиента при подключении к службам в случаях, когда требуется взаимная проверка подлинности.Данный раздел можно использовать для задания сертификатов служб для сценариев, где клиент должен обеспечить защиту сообщений, передаваемых службе, с помощью сертификатов службы.  
  
 В рамках сценария федерации также можно настроить в клиенте использование токенов, выданных безопасной службой токенов или локальным источником токенов.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о федеративных сценариях см. раздел [Федерация и выданные маркеры](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)Все учетные данные клиентов находятся в разделе [\<endpointBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md), как показано в следующем коде.  
  
```  
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
  
#### Элемент \<clientCertifictate\>  
 Задает сертификат, используемый для проверки подлинности клиента с помощью этого элемента.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Практическое руководство. Задание значений учетных данных клиента](../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
#### \<httpDigest\>  
 Эта функция должна быть включена с помощью Active Directory в Windows и службах IIS.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Дайджест\-проверка подлинности в IIS 6.0](http://go.microsoft.com/fwlink/?LinkId=88443).  
  
#### Элемент \<issuedToken\>  
 [\<issuedToken\>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) содержит элементы, используемые для настройки локального издателя маркеров, или поведений, используемых со службой маркеров безопасности.Инструкции по настройке клиента на работу с локальным издателем см. в разделе [Как настраивать локальный издатель](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).  
  
#### \<localIssuerAddress\>  
 Задает адрес службы маркеров безопасности по умолчанию.Этот адрес используется, если <xref:System.ServiceModel.WSFederationHttpBinding> не предоставляет URL\-адрес для службы маркеров безопасности или если адрес издателя федеративной привязки имеет значение http:\/\/schemas.microsoft.com\/2005\/12\/ServiceModel\/Addressing\/Anonymous либо `null`.В этих случаях необходимо настроить объект <xref:System.ServiceModel.Description.ClientCredentials> с использованием адреса локального издателя и привязки, с помощью которой будет осуществляться взаимодействие с этим издателем.  
  
#### \<issuerChannelBehaviors\>  
 [\<issuerChannelBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md) [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] служит для добавления поведений клиента, которые будут использоваться при взаимодействии со службой маркеров безопасности.Поведения клиента определяются в разделе [\<endpointBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md).Чтобы использовать определенное поведение, добавьте элемент \<`add`\> в элемент `<issuerChannelBehaviors>` с двумя атрибутами.Задайте в атрибуте `issuerAddress` URL\-адрес службы маркеров безопасности, а в атрибуте `behaviorConfiguration` — имя определенного поведения конечной точки, как показано в следующем примере.  
  
```  
<clientCredentials>  
   <issuedToken>  
      <issuerChannelBehaviors>  
         <add issuerAddress="http://www.contoso.com"  
               behaviorConfiguration="clientBehavior1" />     
```  
  
#### Элемент \<serviceCertificate\>  
 Этот элемент служит для управления проверкой подлинности сертификатов службы.  
  
 В элементе [\<defaultCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md) может храниться один сертификат, используемый, если служба не указала никакого сертификата.  
  
 Используйте [\<scopedCertificates\>](../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)[\<добавление;\>](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md) и для задания сертификатов службы, связанных с определенными службами.Элемент `<add>` содержит атрибут `targetUri`, который служит для связывания сертификата со службой.  
  
 Элемент [\<аутентификация\>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) указывает уровень доверия, который используется при проверке подлинности сертификатов.По умолчанию для уровня устанавливается значение «ChainTrust», указывающее, что каждый сертификат должен находиться в иерархии сертификатов, которая на самом верху цепи завершается доверенным центром сертификации.Это наиболее безопасный режим.Также можно установить значение PeerOrChainTrust. В этом случае будут приниматься как самостоятельно выдаваемые сертификаты \(доверие одноранговой группы\), так и сертификаты, которые находятся в цепочке доверия.Данное значение используется при разработке и отладке клиентов и служб, так как самостоятельно выданные сертификаты не нужно приобретать у доверенного центра сертификации.При развертывании клиента вместо этого значения следует использовать значение "ChainTrust".Также можно задать значение "Custom" или "None". Чтобы использовать значение "Custom", необходимо также установить для атрибута `CustomCertificateValidatorType` значение сборки и типа, которые используются при проверке сертификата.Для создания собственного пользовательского модуля проверки необходимо наследование от абстрактного класса <xref:System.IdentityModel.Selectors.X509CertificateValidator>.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
 Элемент [\<аутентификация\>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)`RevocationMode содержит атрибут` , который указывает способ проверки отзыва сертификатов.По умолчанию используется значение online, которое указывает, что проверка отзыва сертификата выполняется автоматически.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
## ServiceAuthorization  
 Элемент [\<serviceAuthorization\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) содержит элементы, влияющие на авторизацию, поставщики пользовательских ролей и олицетворение.  
  
 Класс <xref:System.Security.Permissions.PrincipalPermissionAttribute> применяется к методу службы.Этот атрибут указывает группы пользователей, которые следует использовать при авторизации использования защищенного метода.Значение по умолчанию — "UseWindowsGroups". Оно указывает, что при попытке доступа к ресурсу поиск идентификации выполняется в таких группах Windows, как "Администраторы" или "Пользователи".Также можно задать атрибут UseAspNetRoles для использования поставщика пользовательской роли, который настроен в элементе \<`system.web`\>, как показано в следующем коде.  
  
```  
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
  
```  
<behaviors>  
 <behavior name="ServiceBehaviour">          
  <serviceAuthorization principalPermissionMode ="UseAspNetRoles"   
                        roleProviderName ="SqlProvider" />  
</behavior>   
   <!-- Other configuration code not shown. -->  
</behaviors>  
```  
  
## Настройка аудита безопасности  
 [\<serviceSecurityAudit\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) служит для задания журнала, в который производится запись, и типов регистрируемых событий.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Аудит](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
```  
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
  
## Безопасный обмен метаданными  
 Экспорт метаданных в клиенты удобен для разработчиков служб и клиентов, так как позволяет загружать конфигурацию и код клиента.Для снижения подверженности службы действиям недобросовестных пользователей перенос можно защитить с помощью механизма SSL по протоколу HTTP \(HTTPS\).Для этого необходимо вначале выполнить привязку подходящего сертификата X.509 к конкретному порту компьютера, на котором размещена служба.\([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).\) Затем добавьте в конфигурацию службы элемент [\<serviceMetadata\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md)`HttpsGetEnabled` и задайте для атрибута `true` значение .После этого следует присвоить атрибуту `HttpsGetUrl` URL\-адрес конечной точки метаданных службы, как показано в следующем примере.  
  
```  
<behaviors>  
 <serviceBehaviors>  
  <behavior name="NewBehavior">  
    <serviceMetadata httpsGetEnabled="true"   
     httpsGetUrl="https://myComputerName/myEndpoint" />  
  </behavior>  
 </serviceBehaviors>  
</behaviors>  
```  
  
## См. также  
 [Аудит](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)   
 [Модель безопасности для Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x419)