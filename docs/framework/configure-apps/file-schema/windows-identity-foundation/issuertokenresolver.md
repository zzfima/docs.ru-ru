---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 67d7e0aa5b6b05bfe8b17a1b1efebb1fbddbb0eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152675"
---
# <a name="issuertokenresolver"></a>\<issuerTokenResolver>
Регистрирует токен-решателя эмитента, который используется обработчиками в коллекции обработчиков токенов. Разрешители маркеров эмитента используются для разрешения маркера подписи на входящих токенах и сообщениях.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityМодель>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<идентичностьНастройка>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenhandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**  
  
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
  
|attribute|Описание|  
|---------------|-----------------|  
|type|Определяет тип разрешительного маркера эмитента. Должен быть <xref:System.IdentityModel.Tokens.IssuerTokenResolver> либо класс, либо тип, <xref:System.IdentityModel.Tokens.IssuerTokenResolver> который вытекает из класса. Обязательный элемент.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 None  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<securityTokenhandlerConfiguration>](securitytokenhandlerconfiguration.md)|Обеспечивает конфигурацию для сбора обработчиков маркеров безопасности.|  
  
## <a name="remarks"></a>Remarks  
 Разрешители маркеров эмитента используются для разрешения маркера подписи на входящих токенах и сообщениях. Он используется для извлечения криптографического материала, который используется для проверки подписи. Необходимо указать `type` атрибут. Указанный тип может <xref:System.IdentityModel.Tokens.IssuerTokenResolver> быть либо или пользовательским <xref:System.IdentityModel.Tokens.IssuerTokenResolver> типом, который вытекает из класса.  
  
 Некоторые обработчики токенов позволяют указывать настройки маркера эмитента в конфигурации. Настройки отдельных обработчиков маркеров переопределяют те, которые указаны в коллекции обработчика маркеров безопасности.  
  
> [!NOTE]
> Определение элемента `<issuerTokenResolver>` в качестве элемента ребенка [ \<идентификационных конфигураций>](identityconfiguration.md) элемента было изуродовано, но по-прежнему поддерживается для обратной совместимости. Настройки элемента `<securityTokenHandlerConfiguration>` переопределяют элементы на элементе. `<identityConfiguration>`  
  
## <a name="example"></a>Пример  
 В следующем XML отображается конфигурация для разрешительного маркера эмитента, <xref:System.IdentityModel.Tokens.IssuerTokenResolver>основанная на пользовательском классе, который вытекает из. Разрешители токенов поддерживают словарь пар ключей аудитории, который инициализирован из пользовательского элемента конфигурации (),`<AddAudienceKeyPair>`определенного для класса. Класс переопределяет <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> метод обработки этого элемента. Переопределение отображается в следующем примере; однако методы, которые он называет, не отображаются для краткости. Для полного примера `CustomToken` смотрите пример.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
