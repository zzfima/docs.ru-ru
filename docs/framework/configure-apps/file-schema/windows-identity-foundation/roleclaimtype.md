---
title: "&lt;roleClaimType&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;roleClaimType&gt;
Определяет утверждение, указывающее роль утверждений типа в коллекции объектов <xref:System.Security.Claims.ClaimsIdentity>, возвращаемых методом <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> обработчика токена.  
  
## Синтаксис  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <roleClaimType value=xs:string>  
          </roleClaimType>  
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
|value|Строка, задающая универсальный код ресурса \(uri\), представляющий тип утверждения claim использовать для роли утверждения.|  
  
### Дочерние элементы  
 None  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<samlSecurityTokenRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|Предоставляет конфигурацию для класса <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> или производного класса из этих классов.|  
  
## Заметки  
 Наборы элементов `<roleClaimType>` свойство <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>, когда объект <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> будет инициализировать из конфигурации.  
  
## Пример  
  
```  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## См. также  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>