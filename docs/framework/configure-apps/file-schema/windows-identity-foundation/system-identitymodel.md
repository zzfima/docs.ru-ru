---
title: '&lt;system.identityModel&gt;'
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6faeadc9fcdffc8c8aa14fdcc744896b45a941f0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755257"
---
# <a name="ltsystemidentitymodelgt"></a>&lt;system.identityModel&gt;
Обеспечивает настройку для включения параметров Windows Identity Foundation (WIF) в приложениях.  
  
 \<system.identityModel >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Указывает параметры уровня службы удостоверений.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`<configuration>`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
  
## <a name="remarks"></a>Примечания  
 Добавить `<system.identityModel>` раздел в файл конфигурации для настройки службы или приложения для использования Windows Identity Foundation (WIF). `<system.identityModel>` Представлен <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> класса.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует добавление `<system.identityModel>` раздела в файле конфигурации. Сначала необходимо добавить объявление раздела и пространство имен конфигурации в разделе `<configSections>` элемента. Затем можно добавить `<system.IdentityModel>` элемент в файл конфигурации, чтобы указать одну или несколько конфигураций удостоверения.  
  
```xml  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
