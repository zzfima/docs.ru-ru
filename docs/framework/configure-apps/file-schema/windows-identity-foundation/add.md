---
title: '&lt;add&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: c0709159207cfd9f32aa9b6243bb53b7c1ed0e3d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt"></a>&lt;add&gt;
Добавляет обработчик маркеров безопасности в коллекцию обработчиков токенов.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<add>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
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
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|type|Имя типа CLR обработчик маркеров для добавления. Дополнительные сведения о способах указания `type` см. в разделе [ссылок на пользовательские типы](http://msdn.microsoft.com/en-us/7286d2e3-c63d-49fd-abdc-ce2705f22c24).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|Обеспечивает настройку для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса или производного класса от любого из этих классов.|  
|[\<sessionTokenRequirement >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|Обеспечивает настройку для <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> класса или производных классов.|  
|[\<userNameSecurityTokenHandlerRequirement >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|Обеспечивает настройку для <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> класса или производных классов.|  
|[\<x509SecurityTokenHandlerRequirement >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|Предоставляет дополнительной конфигурации <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> класса или производных классов.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<securityTokenHandlers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Задает коллекцию обработчиков токенов безопасности, которые зарегистрированы с конечной точкой.|  
  
## <a name="remarks"></a>Примечания  
 `<add>` Элемент может занять один дочерний элемент, указывающий конфигурацию для обработчика токенов. Это зависит от того, является ли ссылка на класс обработчика через `type` атрибут `<add>` обеспечивает поддержку этой функции. Классы обработчика токенов, которые поддерживают эту функцию должен предоставлять конструктор, принимающий <xref:System.Xml.XmlElement> объекта.  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 Несколько классов обработчика токенов встроенных средств безопасности предоставляет эту функцию. Эти классы являются <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, и <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.  
  
> [!IMPORTANT]
>  Коллекция обработчика токенов может содержать только один обработчик любого конкретного типа. Это означает, например, что если вы хотите добавить обработчик, который является производным от <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса в коллекцию, необходимо сначала удалить <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, который по умолчанию присутствует, из коллекции. Можно использовать [ \<удалить >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) элемента, который требуется удалить из коллекции или использовать один обработчик [ \<снимите >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) элемента, который требуется удалить из коллекции все обработчики.  
  
 Эквивалентные параметры, заданные в коллекцию обработчиков токенов в разделе переопределить параметры, заданные в обработчик [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) элемент и теми, которые указаны на уровне службы в группе [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемента.  
  
## <a name="example"></a>Пример  
 Следующий XML-КОДЕ показано использование `<add>` и `<remove>` элементов для замены токенов обработчик сеанса по умолчанию обработчик маркеров пользовательского сеанса. XML-код будет браться из `ClaimsAwareWebFarm` образца.  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
