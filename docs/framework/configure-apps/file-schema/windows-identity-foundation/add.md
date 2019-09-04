---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 932e8452542ace66824fba1262694c220ce88676
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252189"
---
# <a name="add"></a>\<add>
Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**  
  
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
|type|Имя типа CLR обработчика токенов, который необходимо добавить. Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement >](samlsecuritytokenrequirement.md)|Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , класса или производного класса любого из этих классов.|  
|[\<Сессионтокенрекуиремент >](sessiontokenrequirement.md)|Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> класса или производных классов.|  
|[\<Усернамесекурититокенхандлеррекуиремент >](usernamesecuritytokenhandlerrequirement.md)|Предоставляет конфигурацию для <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> класса или производных классов.|  
|[\<x509SecurityTokenHandlerRequirement >](x509securitytokenhandlerrequirement.md)|Предоставляет необязательную конфигурацию для <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> класса или производных классов.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<securityTokenHandlers >](securitytokenhandlers.md)|Указывает коллекцию обработчиков маркеров безопасности, зарегистрированных в конечной точке.|  
  
## <a name="remarks"></a>Примечания  
 `<add>` Элемент может принимать один дочерний элемент, указывающий конфигурацию для обработчика маркеров. Это зависит от того, поддерживает ли эта функция класс обработчика, на `<add>` который ссылается `type` атрибут элемента. Классы обработчиков маркеров, которые предоставляют эту функцию, должны предоставлять конструктор, <xref:System.Xml.XmlElement> принимающий объект.  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 Некоторые из встроенных классов обработчиков маркеров безопасности предоставляют эту функцию. Эти классы: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> ,<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>,, и<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>. <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>  
  
> [!IMPORTANT]
> Коллекция обработчиков маркеров может содержать только один обработчик любого заданного типа. Это означает, например, что если требуется добавить обработчик, производный от <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса, в коллекцию, необходимо сначала удалить объект <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, который существует по умолчанию, из коллекции. Можно использовать [ \<элемент remove >](remove.md) для удаления одного обработчика из [ \<](clear.md) коллекции или использовать элемент clear > для удаления всех обработчиков из коллекции.  
  
 Параметры, заданные для обработчика, переопределяют эквивалентные параметры, указанные в коллекции обработчика маркеров в [ \<элементе > секурититокенхандлерконфигуратион](securitytokenhandlerconfiguration.md) , и те, которые указаны на уровне службы в разделе [ \< Элемент > identityConfiguration](identityconfiguration.md) .  
  
## <a name="example"></a>Пример  
 В следующем коде XML показано использование `<add>` элементов и `<remove>` для замены обработчика токена сеанса по умолчанию обработчиком пользовательского маркера сеанса. XML взят из `ClaimsAwareWebFarm` примера.  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
