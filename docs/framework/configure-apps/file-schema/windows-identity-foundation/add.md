---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: cb88d2a37740cf439f4fd2aa0f7fe4c098da1cf2
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269761"
---
# <a name="add"></a>\<add>
Добавляет обработчик токенов безопасности в коллекцию обработчиков токенов.  
  
 \<system.identityModel>  
\<identityConfiguration>  
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
|type|Имя типа CLR обработчик токенов для добавления. Дополнительные сведения о способах указания `type` атрибут, см. в разделе [ссылок на пользовательские типы](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класс или класс, производный от любого из этих классов.|  
|[\<sessionTokenRequirement >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> классом или производными классами.|  
|[\<userNameSecurityTokenHandlerRequirement >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|Предоставляет конфигурацию для <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> классом или производными классами.|  
|[\<x509SecurityTokenHandlerRequirement >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|Предоставляет вариант конфигурации <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> классом или производными классами.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<securityTokenHandlers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Задает коллекцию обработчиков токенов безопасности, которые зарегистрированы с конечной точкой.|  
  
## <a name="remarks"></a>Примечания  
 `<add>` Элемент может занять один дочерний элемент, указывающий конфигурацию для обработчика маркеров. Это зависит от того, является ли ссылка на класс обработчика через `type` атрибут `<add>` обеспечивает поддержку этой функции. Классов для обработчиков маркеров, которые предоставляют этот компонент должен предоставлять конструктор, принимающий <xref:System.Xml.XmlElement> объекта.  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 Некоторые из классов для обработчиков маркеров встроенных средств безопасности предоставляет такой возможности. Эти классы являются <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, и <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.  
  
> [!IMPORTANT]
>  Коллекция обработчиков токенов может содержать только один обработчик любого заданного типа. Это означает, например, что если вы хотите добавить обработчик, который является производным от <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса в коллекцию, необходимо сначала удалить <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, который присутствует по умолчанию из коллекции. Можно использовать [ \<удалить >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) элемент нужно удалить из коллекции или использовать один обработчик [ \<снимите >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) элемент нужно удалить все обработчики из коллекции.  
  
 Настройки, указанные на обработчик переопределяют аналогичные параметры, указанные на коллекцию обработчиков токенов в разделе [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) элемент и теми, которые указаны на уровне службы в разделе [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент.  
  
## <a name="example"></a>Пример  
 Следующий код XML показывает использование `<add>` и `<remove>` элементов для замены маркера обработчик сеанса по умолчанию обработчик токенов пользовательского сеанса. XML-код взят из `ClaimsAwareWebFarm` образца.  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
