---
title: "&lt;issuerNameRegistry&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 12
---
# &lt;issuerNameRegistry&gt;
Настройка реестра имя поставщика, используемый в коллекцию обработчиков маркеров обработчики.  
  
## Синтаксис  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
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
|type|Тип, производный от <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса.  Дополнительные сведения об указании пользовательского `type`, см. [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<trustedIssuers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|При `type` атрибут указывает имя реестра на основе конфигурации поставщика \( <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класс\), [\<trustedIssuers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) элемент должен быть указан.  [\<trustedIssuers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) Может принимать элемент `<add>`, `<clear>`, или `<remove>` элементы, как дочерние элементы.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Содержит настройки для коллекции безопасности обработчиков маркеров.|  
  
## Заметки  
 Все маркеры поставщика проверяются с помощью реестра имя поставщика.  Это объект, производный от <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса.  В реестре имя поставщика используется для связывания мнемонический имя криптографического материала, необходимые для проверки подписей маркеров, создаваемых соответствующего поставщика.  Реестр имен поставщиков поддерживает список поставщиков, которые являются доверенными доверяющей стороной \(RP\) приложения.  Тип реестра имя поставщика задается с помощью `type` атрибут.  `<issuerNameRegistry>` Элемент может иметь дочерние элементы, которые обеспечивают настройку для указанного типа.  Предоставляет логику, которая обрабатывает эти дочерние элементы путем переопределения <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> метод.  
  
 WIF предоставляет один поставщик реестра введите имя изначально, <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса.  Этот класс использует набор сертификатов доверенного поставщика, указанного в конфигурации.  Требуется дочерний элемент конфигурации, `<trustedIssuers>`, в которой настроен коллекцию сертификатов доверенного поставщика.  Доверенные сертификаты указаны с использованием ASN.1 кодировке формы отпечаток сертификата и при добавлении или удалении из коллекции с помощью `<add>`, `<clear>`, или `<remove>` элементов.  
  
 `<issuerNameRegistry>` Представленного элементом <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> класса.  
  
> [!NOTE]
>  Указание `<issuerNameRegistry>` элемент как дочерний элемент [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по\-прежнему поддерживается для обратной совместимости.  Параметры на `<securityTokenHandlerConfiguration>` элементов заменяют на `<identityConfiguration>` элемент.  
  
## Пример  
 Следующий код XML показано, как указать поставщика на основе конфигурации реестра имя.  
  
```  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
  
```  
  
## См. также  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>   
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>