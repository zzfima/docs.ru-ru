---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: da591940910b16d42ef8ab1a05c4b244dbe543f4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942630"
---
# <a name="issuertokenresolver"></a>\<issuerTokenResolver>
Регистрирует сопоставитель маркеров издателя, используемый обработчиками в коллекции обработчиков маркеров. Сопоставитель токенов издателя используется для разрешения маркера подписывания входящих токенов и сообщений.  
  
 \<> System. identityModel  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<Секурититокенхандлерконфигуратион >  
\<issuerTokenResolver>  
  
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
|type|Указывает тип сопоставителя маркеров издателя. Должен быть либо <xref:System.IdentityModel.Tokens.IssuerTokenResolver> классом, либо типом, производным <xref:System.IdentityModel.Tokens.IssuerTokenResolver> от класса. Обязательный.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Секурититокенхандлерконфигуратион >](securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.|  
  
## <a name="remarks"></a>Примечания  
 Сопоставитель токенов издателя используется для разрешения маркера подписывания входящих токенов и сообщений. Он используется для получения криптографического материала, используемого для проверки подписи. Необходимо указать `type` атрибут. Указанный тип может быть либо <xref:System.IdentityModel.Tokens.IssuerTokenResolver> либо пользовательским типом, производным <xref:System.IdentityModel.Tokens.IssuerTokenResolver> от класса.  
  
 Некоторые обработчики маркеров позволяют задавать параметры сопоставителя маркеров издателя в конфигурации. Параметры отдельных обработчиков маркеров переопределяют те, которые указаны в коллекции обработчика маркеров безопасности.  
  
> [!NOTE]
> Указание элемента в качестве дочернего элемента [ \<элемента > identityConfiguration](identityconfiguration.md) является устаревшим, но по-прежнему поддерживается для обратной совместимости. `<issuerTokenResolver>` Параметры элемента переопределяют их `<identityConfiguration>` для элемента. `<securityTokenHandlerConfiguration>`  
  
## <a name="example"></a>Пример  
 В следующем коде XML показана конфигурация для сопоставителя маркеров издателя, основанного на пользовательском классе, производном от <xref:System.IdentityModel.Tokens.IssuerTokenResolver>. Сопоставитель токенов поддерживает словарь пар ключей аудитории, которые инициализируются из настраиваемого элемента конфигурации (`<AddAudienceKeyPair>`), определенного для класса. Класс переопределяет <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> метод для обработки этого элемента. Переопределение показано в следующем примере. Однако методы, которые он вызывает, не отображаются для краткости. Полный пример см. в `CustomToken` примере.  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a>Пример  
  
```  
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
