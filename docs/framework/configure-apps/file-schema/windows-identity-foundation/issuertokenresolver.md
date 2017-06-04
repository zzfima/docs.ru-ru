---
title: "&lt;issuerTokenResolver&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# &lt;issuerTokenResolver&gt;
Регистрирует поставщика Распознавателю маркеров, используемые в коллекцию обработчиков маркеров обработчики.  Распознавателю маркеров поставщика используется для разрешения подписи маркера для входящих сообщений и лексем.  
  
## Синтаксис  
  
```  
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
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|type|Задает тип поставщика Распознавателю маркеров.  Должен быть либо <xref:System.IdentityModel.Tokens.IssuerTokenResolver> класса или типа, производного от <xref:System.IdentityModel.Tokens.IssuerTokenResolver> класса.  Дополнительные сведения об указании `type` атрибута см [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).  Обязательный.|  
  
### Дочерние элементы  
 None  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Содержит настройки для коллекции безопасности обработчиков маркеров.|  
  
## Заметки  
 Распознавателю маркеров поставщика используется для разрешения подписи маркера для входящих сообщений и лексем.  Он используется для извлечения криптографического материала, используемый для проверки подписи.  Необходимо указать `type` атрибут.  Может быть указан тип <xref:System.IdentityModel.Tokens.IssuerTokenResolver> или пользовательского типа, производного от <xref:System.IdentityModel.Tokens.IssuerTokenResolver> класса.  
  
 Некоторые обработчики маркеров позволяют указать поставщика Распознавателю маркеров параметров конфигурации.  Параметры на отдельных обработчиков маркеров вместо указанной коллекции обработчик маркеров безопасности.  
  
> [!NOTE]
>  Указание `<issuerTokenResolver>` элемент как дочерний элемент [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по\-прежнему поддерживается для обратной совместимости.  Параметры на `<securityTokenHandlerConfiguration>` элементов заменяют на `<identityConfiguration>` элемент.  
  
## Пример  
 Следующий код XML показывает конфигурацию для сопоставления имен поставщика маркера, основанный на пользовательский класс, производный от <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.  Распознавателю маркеров поддерживает словарь пар ключ аудитории, инициализируется из настраиваемых элементов конфигурации \(`<AddAudienceKeyPair>`\), определенные для класса.  Класс переопределяет <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> метод для данного элемента.  Переопределение показано в следующем примере; Тем не менее он вызывает методы для краткости не отображаются.  Полный пример см. `CustomToken` образца.  
  
```  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## Пример  
  
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
  
## См. также  
 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>