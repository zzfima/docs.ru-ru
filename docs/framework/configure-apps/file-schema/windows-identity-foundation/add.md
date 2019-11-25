---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 83ba51cbbd5100bf7412f9914a270cac88f7faa1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973805"
---
# <a name="add"></a>\<add>
Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<добавить >**  
  
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
|тип|Имя типа CLR обработчика токенов, который необходимо добавить. Дополнительные сведения об указании атрибута `type` см. в разделе [ссылки на пользовательские типы](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement >](samlsecuritytokenrequirement.md)|Предоставляет конфигурацию для класса <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> или производного класса любого из этих классов.|  
|[\<Сессионтокенрекуиремент >](sessiontokenrequirement.md)|Предоставляет конфигурацию для класса <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> или производных классов.|  
|[\<Усернамесекурититокенхандлеррекуиремент >](usernamesecuritytokenhandlerrequirement.md)|Предоставляет конфигурацию для класса <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> или производных классов.|  
|[\<x509SecurityTokenHandlerRequirement >](x509securitytokenhandlerrequirement.md)|Предоставляет необязательную конфигурацию для класса <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> или производных классов.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<securityTokenHandlers >](securitytokenhandlers.md)|Указывает коллекцию обработчиков маркеров безопасности, зарегистрированных в конечной точке.|  
  
## <a name="remarks"></a>Заметки  
 Элемент `<add>` может принимать один дочерний элемент, указывающий конфигурацию для обработчика маркеров. Это зависит от того, поддерживает ли этот компонент класс обработчика, на который ссылается атрибут `type` элемента `<add>`. Классы обработчиков маркеров, которые предоставляют эту функцию, должны предоставлять конструктор, принимающий объект <xref:System.Xml.XmlElement>.  

```csharp  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 Некоторые из встроенных классов обработчиков маркеров безопасности предоставляют эту функцию. Этими классами являются <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>и <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.  
  
> [!IMPORTANT]
> Коллекция обработчиков маркеров может содержать только один обработчик любого заданного типа. Это означает, например, что если нужно добавить в коллекцию обработчик, производный от класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, необходимо сначала удалить <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, который существует по умолчанию, из коллекции. Можно использовать элемент [\<Remove >](remove.md) для удаления одного обработчика из коллекции или использовать [\<Clear >](clear.md) для удаления всех обработчиков из коллекции.  
  
 Параметры, заданные для обработчика, переопределяют эквивалентные параметры, указанные в коллекции обработчика маркеров в элементе [\<секурититокенхандлерконфигуратион >](securitytokenhandlerconfiguration.md) , и те, которые указаны на уровне службы в элементе [\<identityConfiguration >](identityconfiguration.md) .  
  
## <a name="example"></a>Пример  
 В следующем XML-коде показано использование элементов `<add>` и `<remove>` для замены обработчика токенов сеанса по умолчанию обработчиком пользовательского маркера сеанса. XML взят из примера `ClaimsAwareWebFarm`.  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
