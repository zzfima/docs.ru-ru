---
title: "&lt;trustedIssuers&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;trustedIssuers&gt;
Настройка списка сертификатов доверенного поставщика, имя реестр на основе конфигурации поставщика \(<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>\).  
  
## Синтаксис  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
 None  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`<add thumbprint=xs:string name=xs:string>`|Добавляет сертификат в коллекцию доверенных поставщиков.  Указанный сертификат с `thumbprint` атрибут.  Этот атрибут является обязательным и должен содержать форму в кодировке ASN.1 отпечаток сертификата.  `name` Атрибут является необязательным и может использоваться для указания понятное имя для сертификата.|  
|`<clear>`|Очищает все сертификаты из коллекции доверенных поставщиков.|  
|`<remove thumbprint=xs:string>`|Удаляет сертификат из коллекции доверенных поставщиков.  Указанный сертификат с `thumbprint` атрибут.  Это обязательный атрибут.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<issuerNameRegistry\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Настройка реестра имя поставщика. **Important:**  `type` Атрибута `<issuerNameRegistry>` элемент должен ссылаться на <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса для `<trustedIssuers>` элемент недействителен.|  
  
## Заметки  
 Основу удостоверение Windows \(WIF\) предоставляет одну реализацию <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класс изначально, <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса.  В системном реестре имя поставщика ведет список доверенных поставщиков, которые загружаются из конфигурации.  Список связывает имя каждого поставщика с сертификат X.509, который необходим для проверки подписей маркеров, создаваемых поставщиком.  Список доверенных издателей указан в разделе `<trustedIssuers>` элемент.  Каждый элемент в списке связывает имя мнемонический поставщика сертификата X.509, необходимый для проверки подписей маркеров, создаваемых этого поставщика.  Доверенных сертификатов указаны с использованием ASN.1 кодировке формы отпечаток сертификата и добавлении коллекции с помощью `<add>` элемент.  Можно очистить или удалить поставщиков \(сертификаты\) из списка с помощью `<clear>` и `<remove>` элементов.  
  
 `type` Атрибута `<issuerNameRegistry>` элемент должен ссылаться на <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса для `<trustedIssuers>` элемент недействителен.  
  
## Пример  
 Следующий код XML показано, как указать поставщика на основе конфигурации реестра имя.  
  
```  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
  
```  
  
## См. также  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>   
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>