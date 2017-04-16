---
title: "&lt;nameClaimType&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;nameClaimType&gt;
Задает тип утверждения, которое указывает свойство <xref:System.Security.Principal.IIdentity.Name%2A>.  Утверждение используется для поиска <xref:System.Security.Claims.Claim> в коллекции объектов <xref:System.Security.Claims.ClaimsIdentity>, возвращаемых методом <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> этого обработчика токена.  Значение соответствующего утверждения затем помещаются в качестве имени <xref:System.Security.Principal.IIdentity> созданного из этого обработчика токена.  
  
## Синтаксис  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|value|Строка, задающая универсальный код ресурса \(uri\), представляющий утверждение утверждения использовать для свойства <xref:System.Security.Principal.IIdentity.Name%2A>.  Обязательный.|  
  
### Дочерние элементы  
 None  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<samlSecurityTokenRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|Предоставляет конфигурацию для класса <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> или производного класса из этих классов.|  
  
## Заметки  
 Наборы элементов `<nameClaimType>` свойство <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>, когда объект <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> будет инициализировать из конфигурации.  
  
## Пример  
  
```  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## См. также  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>