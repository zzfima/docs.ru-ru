---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 451750a1facd9a886b53427a8d54580d1a939fa5
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968513"
---
# <a name="issuertokenresolver"></a>\<Иссуертокенресолвер >
Регистрирует сопоставитель маркеров издателя, используемый обработчиками в коллекции обработчиков маркеров. Сопоставитель токенов издателя используется для разрешения маркера подписывания входящих токенов и сообщений.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<секурититокенхандлерконфигуратион >** ](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<иссуертокенресолвер >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|тип|Указывает тип сопоставителя маркеров издателя. Должен быть либо классом <xref:System.IdentityModel.Tokens.IssuerTokenResolver>, либо типом, производным от класса <xref:System.IdentityModel.Tokens.IssuerTokenResolver>. Обязательный.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Секурититокенхандлерконфигуратион >](securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.|  
  
## <a name="remarks"></a>Заметки  
 Сопоставитель токенов издателя используется для разрешения маркера подписывания входящих токенов и сообщений. Он используется для получения криптографического материала, используемого для проверки подписи. Необходимо указать атрибут `type`. Указанный тип может быть либо <xref:System.IdentityModel.Tokens.IssuerTokenResolver>, либо настраиваемого типа, производного от класса <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.  
  
 Некоторые обработчики маркеров позволяют задавать параметры сопоставителя маркеров издателя в конфигурации. Параметры отдельных обработчиков маркеров переопределяют те, которые указаны в коллекции обработчика маркеров безопасности.  
  
> [!NOTE]
> Указание элемента `<issuerTokenResolver>` в качестве дочернего элемента элемента [\<identityConfiguration >](identityconfiguration.md) является устаревшим, но по-прежнему поддерживается для обеспечения обратной совместимости. Параметры элемента `<securityTokenHandlerConfiguration>` переопределяют их в элементе `<identityConfiguration>`.  
  
## <a name="example"></a>Пример  
 В следующем коде XML показана конфигурация для сопоставителя маркеров издателя, основанного на пользовательском классе, производном от <xref:System.IdentityModel.Tokens.IssuerTokenResolver>. Сопоставитель токенов поддерживает словарь пар ключей аудитории, которые инициализируются из настраиваемого элемента конфигурации (`<AddAudienceKeyPair>`), определенного для класса. Класс переопределяет метод <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> для обработки этого элемента. Переопределение показано в следующем примере. Однако методы, которые он вызывает, не отображаются для краткости. Полный пример см. в примере `CustomToken`.  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a>Пример
  
```csharp
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
``` 
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
