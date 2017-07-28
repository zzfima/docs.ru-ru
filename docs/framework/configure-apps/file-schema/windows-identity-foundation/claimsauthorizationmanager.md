---
title: "&lt;claimsAuthorizationManager&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;claimsAuthorizationManager&gt;
Регистрирует диспетчер авторизации заявок для входящих утверждений.  
  
## Синтаксис  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|type|Пользовательский тип, производный от <xref:System.Security.Claims.ClaimsAuthorizationManager> класса.  Дополнительные сведения об указании `type` атрибута см [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).|  
  
### Дочерние элементы  
 Если не `type` атрибут, или, если `type` атрибут ссылки на <xref:System.Security.Claims.ClaimsAuthenticationManager> класс, `<claimsAuthorizationManager>` элемент не принимает дочерние элементы; Тем не менее, классы, производные от <xref:System.Security.Claims.ClaimsAuthorizationManager> можно определить дочерние элементы конфигурации.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Задает параметры уровня службы удостоверений.|  
  
## Заметки  
 Поведение по умолчанию, предоставляемые через <xref:System.Security.Claims.ClaimsAuthorizationManager> класса всегда выполняет авторизацию входящих утверждений.  Если не `type` указанный атрибут или, если `type` атрибут указывает, <xref:System.Security.Claims.ClaimsAuthorizationManager> класс, `<claimsAuthorizationManager>` дочерние элементы элемента не принимает.  Можно указать `type` атрибут, чтобы зарегистрировать тип производным от <xref:System.Security.Claims.ClaimsAuthorizationManager> класса, чтобы реализовать пользовательское поведение.  Производные классы поддерживают настройку с помощью дочерних элементов `<claimsAuthorizationManager>` элемент, переопределяя <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> метод для обработки этих элементов.  Схемы, определенные для дочерних элементов — конструктор класса.  
  
> [!IMPORTANT]
>  При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса для обеспечения контроля доступа на основе заявок в коде конфигурации identity, на который ссылается `<federationConfiguration>` элемент настраивает диспетчер авторизации заявок и политики, который используется для принятия решения об авторизации.  Это верно даже в ситуациях, которые не являются пассивный веб\-сценариев, например приложения Windows Communication Foundation \(WCF\) или приложение, которое не является веб.  Если приложение не является пассивным веб\-приложения `<claimsAuthorizationManager>` элемент \(и политики его дочерних элементов, если они есть\) являются только параметры, применяемые конфигурации указанного удостоверения.  Другие параметры не обрабатываются.  Дополнительные сведения см. в описании элемента [\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md).  
  
 Этот элемент задает <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=fullName> свойства.  
  
## Пример  
 Следующий код XML показывает конфигурацию для утверждения авторизации диспетчер, который реализует политику состоят из пар ресурса действие каждый из которых задает логические сочетания утверждений, запрашивающая сторона должен обладать действие на ресурс.  Код, реализующий диспетчер авторизации заявок, может использовать эту политику можно найти в `ClaimsBasedAuthorization` образца.  
  
```  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```