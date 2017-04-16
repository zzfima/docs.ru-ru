---
title: "&lt;add&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;add&gt;
Добавляет в коллекцию обработчиков маркеров обработчик маркеров безопасности.  
  
## Синтаксис  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
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
|type|Имя типа CLR обработчик маркеров для добавления.  Дополнительные сведения об указании `type` атрибута см [Custom Type References](http://msdn.microsoft.com/ru-ru/7286d2e3-c63d-49fd-abdc-ce2705f22c24).|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<samlSecurityTokenRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|Содержит настройки для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класс, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класс или класс, производный от одного из этих классов.|  
|[\<sessionTokenRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|Содержит настройки для <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> класса или производных классов.|  
|[\<userNameSecurityTokenHandlerRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|Содержит настройки для <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> класса или производных классов.|  
|[\<x509SecurityTokenHandlerRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|Предоставляет дополнительные настройки для <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> класса или производных классов.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<securityTokenHandlers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Указывает коллекции обработчиков маркеров безопасности, которые зарегистрированы с конечной точкой.|  
  
## Заметки  
 `<add>` Элемент может занять один дочерний элемент, определяющий конфигурацию для обработчика маркера.  Зависит ли ссылка на класс обработчика через `type` атрибута `<add>` элемент обеспечивает поддержку этой функции.  Классы обработчика маркера, эту функцию должен предоставлять конструктор, принимающий <xref:System.Xml.XmlElement> объект.  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 Некоторые классы обработчика маркера встроенной безопасности обеспечивают эту функциональность.  These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.  
  
> [!IMPORTANT]
>  Обработчик маркеров коллекция может содержать только один обработчик любого заданного типа.  Это означает, например, если требуется добавить обработчик, который является производным от <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса коллекции, необходимо сначала удалить <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, который присутствует по умолчанию, из коллекции.  Можно использовать [\<remove\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) элемента, удаляемого из коллекции или использовать один обработчик [\<clear\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) элемента, удаляемого из коллекции все обработчики.  
  
 Параметры, заданные на обработчик переопределения эквивалентных параметров в коллекцию обработчиков маркеров в [\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) элемент и указанные на уровне службы под [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент.  
  
## Пример  
 Следующий код XML показывает использование `<add>` и `<remove>` элементы для замены обработчика маркера сеанса по умолчанию обработчик маркеров пользовательского сеанса.  XML берется из `ClaimsAwareWebFarm` образца.  
  
```  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```