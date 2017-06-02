---
title: "Модель программирования требований WIF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 149cb875-9b1c-4695-b88a-fbf1725a02f9
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# Модель программирования требований WIF
ASP.NET и Windows Communication Foundation \(WCF\) разработчики обычно используют интерфейсы IIdentity и IPrincipal для работы с данными идентификации.  В.NET 4.5, Foundation удостоверение Windows \(WIF\) интеграции таким образом, что заявки теперь всегда присутствуют для любого участника, как показано на следующей схеме:  
  
 ![Модель программирования требований WIF](../../../docs/framework/security/media/wifclaimsprogrammingmodel.png "WIFClaimsProgrammingModel")  
  
 В.NET 4.5 System.Security.Claims классы новые ClaimsPrincipal и ClaimsIdentity \(см. схему выше\).  Всем участникам.NET теперь являются производными от ClaimsPrincipal.  Все классы встроенных идентификаторов как выполнить… для ASP.NET и WindowsIdentity теперь производными ClaimsIdentity.  Аналогичным образом все встроенные классы участников GenericPrincipal и WindowsPrincipal производными ClaimsPrincipal.  
  
 Заявка представлена <xref:System.Security.Claims.Claim> класса.  Этот класс содержит следующие важные свойства:  
  
-   <xref:System.Security.Claims.Claim.Type%2A>представляет тип заявки и обычно является URI.  Например, представляется утверждение адрес электронной почты `http://schemas.microsoft.com/ws/2008/06/identity/claims/email`.  
  
-   <xref:System.Security.Claims.Claim.Value%2A>содержит значение утверждения и представляется в виде строки.  Например адрес электронной почты может быть представлено как «someone@contoso.com».  
  
-   <xref:System.Security.Claims.Claim.ValueType%2A>представляет тип значения утверждения и обычно является URI.  Например, тип string представляется в виде `http://www.w3.org/2001/XMLSchema#string`.  Введите значение должно быть QName в соответствии с XML\-схемы.  Значение должно иметь формат `namespace#format` для включения WIF допустимое значение QName выходных данных.  Если пространство имен не является строго определенные пространства имен, созданного XML вероятно невозможно схемы проверки, так как не будет опубликованной XSD\-файл для этого пространства имен.  Значение по умолчанию используется тип `http://www.w3.org/2001/XMLSchema#string`.  Пожалуйста, ознакомьтесь с [http:\/\/www.w3.org\/2001\/XMLSchema](http://go.microsoft.com/fwlink/?LinkId=209155) для известного значения типов, можно использовать безопасно.  
  
-   <xref:System.Security.Claims.Claim.Issuer%2A>\-Идентификатор службы маркеров безопасности \(STS\), выдавшего Заявка.  Это может быть представлено как URL\-адрес STS или имя, которое представляет STS, например `https://sts1.contoso.com/sts`.  
  
-   <xref:System.Security.Claims.Claim.OriginalIssuer%2A>Это идентификатор STS, которые первоначально выданы заявки, независимо от того, сколько STSs находятся в цепочке.  Представляется как <xref:System.Security.Claims.Claim.Issuer%2A>.  
  
-   <xref:System.Security.Claims.Claim.Subject%2A>это тема, удостоверение которого проверяется.  Оно содержит <xref:System.Security.Claims.ClaimsIdentity>.  
  
-   <xref:System.Security.Claims.Claim.Properties%2A>Это словарь, который позволяет разработчику предоставить данные приложения для передачи по кабелю вместе с другими свойствами и может быть использован для пользовательской проверки.  
  
## Делегирование идентификации  
 Важным свойством <xref:System.Security.Claims.ClaimsIdentity> , <xref:System.Security.Claims.ClaimsIdentity.Actor%2A>.  Это свойство разрешает делегирование учетных данных в многоуровневой системе действует как клиент отправлять запросы серверной службе среднего уровня.  
  
### Доступ к заявок через Thread.CurrentPrincipal  
 Для доступа к текущему пользователю набор заявок в приложении RP, используйте `Thread.CurrentPrincipal`.  
  
 В следующем примере кода показано использование этого метода для получения System.Security.Claims.ClaimsIdentity:  
  
```  
ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
```  
  
 Дополнительные сведения см. в разделе <xref:System.Security.Claims>.  
  
### Тип заявок роли  
 Настройка приложения RP входит определить, какие роли утверждения должен быть тип.  У этого типа claim используется System.Security.Claims.ClaimsPrincipal.IsInRole\(System.String\).  По умолчанию используется тип заявки `http://schemas.microsoft.com/ws/2008/06/identity/claims/role`.  
  
### Заявки, извлеченные Фондом удостоверение Windows из различных типов маркера  
 WIF поддерживает несколько комбинаций механизмов проверки подлинности, изначально.  В следующей таблице перечислены утверждения, которые WIF извлекает из различных типов маркеров.  
  
||||  
|-|-|-|  
|Тип маркера|Созданные утверждения|Карты В маркер доступа Windows|  
|SAML 1.1|1.  Все заявки от System.IdentityModel.SecurityTokenService.GetOutputClaimsIdentity\(System.Security.Claims.ClaimsPrincipal,System.IdentityModel.Protocols.WSTrust.RequestSecurityToken,System.IdentityModel.Scope\).<br />2.  `http://schemas.microsoft.com/ws/2008/06/identity/claims/confirmationkey` Заявку, содержащую XML\-сериализации ключ подтверждения, если маркер содержит маркер проверки.<br />3.  `http://schemas.microsoft.com/ws/2008/06/identity/claims/samlissuername` Утверждения элемента поставщика.<br />4.  AuthenticationMethod и AuthenticationInstant заявки, если маркер содержит оператор проверки подлинности.|В дополнение к заявок, перечисленных в «SAML 1.1», за исключением утверждения типа `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name`, заявок будет добавлен и удостоверение будет представлен WindowsClaimsIdentity, связанные с проверкой подлинности Windows.|  
|SAML 2.0|Так же, как «SAML 1.1».|Так же, как «SAML 1.1 сопоставляется учетной записи Windows».|  
|X509|1.  Заявки с X 500 различающееся имя, Адрес\_электронной\_почты, dnsName, SimpleName, UpnName, UrlName, отпечаток \(это могут быть извлечены с помощью метода RSACryptoServiceProvider.ExportParameters из свойства X509Certificate2.PublicKey.Key\) RsaKey, DsaKey \(это могут быть извлечены с помощью метода DSACryptoServiceProvider.ExportParameters из свойства X509Certificate2.PublicKey.Key\), свойства X 509 серийный номер сертификата.<br />2.  Утверждение AuthenticationMethod со значением `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/x509`.  Утверждение AuthenticationInstant со значением времени, когда проверки сертификата в формате XmlSchema DateTime.|1.  Использует полное доменное имя учетной записи Windows, как `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name` заявка на значение.  .<br />2.  Заявки от X 509 сертификат не сопоставлен с Windows и заявок от учетной записи windows, полученные путем сопоставления сертификатов Windows.|  
|ИМЯ УЧАСТНИКА\-ПОЛЬЗОВАТЕЛЯ|1.  Заявки, аналогичные заявки в разделе Проверка подлинности Windows.<br />2.  Утверждение AuthenticationMethod со значением `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/password`.  Утверждение AuthenticationInstant со значением времени, если пароль был проверен в формате XmlSchema DateTime.||  
|Windows \(Kerberos или NTLM\)|1.  Заявки, созданный из маркера доступа, например: PrimarySID, DenyOnlyPrimarySID, PrimaryGroupSID, DenyOnlyPrimaryGroupSID, GroupSID, DenyOnlySID и имя<br />2.  AuthenticationMethod со значением `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/windows`.  AuthenticationInstant со значением времени, когда маркера доступа Windows был создан в формате XMLSchema DateTime.||  
|Пары ключей RSA|1.  `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/rsa` Со значением RSAKeyValue утверждения.<br />2.  Утверждение AuthenticationMethod со значением `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/signature`.  Утверждение AuthenticationInstant со значением времени, когда проверяется подлинность ключа RSA \(то есть проверить подпись\) в формате XMLSchema DateTime.||  
  
|||  
|-|-|  
|Тип проверки подлинности|URI в заявку «AuthenticationMethod»|  
|Пароль|`urn:oasis:names:tc:SAML:1.0:am:password`|  
|Kerberos|`urn:ietf:rfc:1510`|  
|SecureRemotePassword|`urn:ietf:rfc:2945`|  
|TLSClient|`urn:ietf:rfc:2246`|  
|X509|`urn:oasis:names:tc:SAML:1.0:am:X509-PKI`|  
|PGP|`urn:oasis:names:tc:SAML:1.0:am:PGP`|  
|Spki|`urn:oasis:names:tc:SAML:1.0:am:SPKI`|  
|XmlDSig|`urn:ietf:rfc:3075`|  
|Не указано|`urn:oasis:names:tc:SAML:1.0:am:unspecified`|