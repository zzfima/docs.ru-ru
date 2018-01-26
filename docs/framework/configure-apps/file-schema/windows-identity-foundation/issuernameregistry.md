---
title: '&lt;issuerNameRegistry&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 7c9b40fb3afb5679496c3cb0dda7821b5b6b0b41
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltissuernameregistrygt"></a>&lt;issuerNameRegistry&gt;
Настройка реестра имя издателя, используемая обработчиков в коллекцию обработчиков токенов.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<securityTokenHandlerConfiguration >  
\<issuerNameRegistry >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
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
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|type|Тип, который является производным от <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса. Дополнительные сведения о том, как задать пользовательский `type`, в разделе [ссылок на пользовательские типы].|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|Когда `type` атрибут задает имя издателя на основе конфигурации реестра ( <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса), [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) должен быть указан элемент. [ \<TrustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) элемент может занять `<add>`, `<clear>`, или `<remove>` элементы в виде дочерних элементов.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Обеспечивает настройку для коллекции безопасности обработчиков маркеров.|  
  
## <a name="remarks"></a>Примечания  
 Все маркеры издателей проверяются с помощью реестра имя издателя. Это объект, который является производным от <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса. Реестр имен поставщиков позволяет связать имя, назначенный криптографические материалы, необходимые для проверки подписи токенов, созданных соответствующего поставщика. Реестр имен поставщиков ведет список издателей, которым доверяют приложения проверяющей стороны (RP). Тип реестра имя поставщика задается с помощью `type` атрибута. `<issuerNameRegistry>` Элемент может иметь один или несколько дочерних элементов, предоставляющих конфигурации для указанного типа. Предоставляют логику, которая обрабатывает эти дочерние элементы, переопределив <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> метод.  
  
 WIF предоставляет одного издателя, имя типа реестра без дополнительной настройки <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса. Этот класс используется набор доверенных издателей сертификатов, которые указаны в конфигурации. Требуется дочерний элемент конфигурации, `<trustedIssuers>`, в которой настроено в коллекцию сертификатов доверенных издателей. Доверенные сертификаты указываются с помощью ASN.1 отпечаток сертификата в кодировке и добавления или удаления из коллекции с помощью `<add>`, `<clear>`, или `<remove>` элементы.  
  
 `<issuerNameRegistry>` Представлен <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> класса.  
  
> [!NOTE]
>  Указание `<issuerNameRegistry>` элемент как дочерний элемент элемента [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по-прежнему поддерживается для обеспечения обратной совместимости. Параметры на `<securityTokenHandlerConfiguration>` элемент переопределяют на `<identityConfiguration>` элемент.  
  
## <a name="example"></a>Пример  
 Следующий код XML показано, как указать поставщика конфигурации на основе реестра имя.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
