---
title: "&lt;system.identityModel&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;system.identityModel&gt;
Содержит настройки для включения параметров Foundation удостоверение Windows \(WIF\) в приложениях.  
  
 \<system.identityModel\>  
  
## Синтаксис  
  
```  
<system.identityModel>  
</system.identityModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
 None  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Задает параметры уровня службы удостоверений.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`<configuration>`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
  
## Заметки  
 Добавить `<system.identityModel>` раздел файла конфигурации, чтобы настроить службу или приложение на использование Foundation удостоверение Windows \(WIF\).  `<system.identityModel>` Представленного элементом <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> класса.  
  
## Пример  
 В этом примере показано, как добавить `<system.identityModel>` раздел в файле конфигурации.  Необходимо сначала добавить объявление раздела и пространство имен конфигурации в разделе `<configSections>` элемент.  Затем можно добавить `<system.IdentityModel>` элемент в файле конфигурации, чтобы указать один или несколько идентификаторов конфигураций.  
  
```  
<configuration>  
  <configSections>  
    <!--WIF 4.5 sections -->  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
  </configSections>  
  
  ...  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost/WebApplication1/" />  
      </audienceUris>  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089">  
        <trustedIssuers>  
          <add thumbprint="313D3B … 9106A9EC" name="SelfSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
      <certificateValidation certificateValidationMode="None"/>  
    </identityConfiguration>  
  </system.identityModel>  
  
  ...  
  
</configuration>  
```  
  
## См. также  
 <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>