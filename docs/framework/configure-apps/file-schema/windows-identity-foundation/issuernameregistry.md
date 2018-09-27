---
title: '&lt;issuerNameRegistry&gt;'
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: de3ceb5d84d17307c69e9155834a0a584e6920a1
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2018
ms.locfileid: "47399167"
---
# <a name="ltissuernameregistrygt"></a>&lt;issuerNameRegistry&gt;
Настраивает реестр имен издателей, используемый обработчиками в коллекцию обработчиков токенов.  
  
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
|type|Тип, который является производным от <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса. Дополнительные сведения о том, как задать пользовательский `type`, см. в разделе [ссылки на пользовательские типы].|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|Когда `type` атрибут задает реестр имен издателей на основе конфигурации ( <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класс), [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) элемент должен быть указан. [ \<TrustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) элемент может занять `<add>`, `<clear>`, или `<remove>` элементы как дочерние элементы.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции безопасности обработчиков маркеров.|  
  
## <a name="remarks"></a>Примечания  
 Все маркеры издателей проверяются с помощью реестра имен издателей. Это объект, который является производным от <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса. Реестр имен издателей используется для сопоставления мнемонического имени с криптографическим материалом, необходимым для проверки подписи токенов, выдаваемых соответствующим издателем. Реестр имен издателей ведет список издателей, которым доверяет приложение проверяющей стороны (RP). Тип реестр имен издателей задается с помощью `type` атрибута. `<issuerNameRegistry>` Элемент может иметь один или несколько дочерних элементов, обеспечивающие конфигурацию для указанного типа. Обеспечивают логику, которая обрабатывает эти дочерние элементы, переопределив <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> метод.  
  
 WIF предоставляет единый издателя тип реестра имя по умолчанию, <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса. Этот класс использует набор доверенных сертификатов издателей, которые указаны в конфигурации. Он требуется дочерний элемент конфигурации, `<trustedIssuers>`, в которой настроено коллекции доверенных сертификатов издателей. Доверенные сертификаты указываются с помощью ASN.1 отпечатка сертификата в кодировке и добавляются или удаляются из коллекции с помощью `<add>`, `<clear>`, или `<remove>` элементов.  
  
 `<issuerNameRegistry>` Элемент, представленный объектом <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> класса.  
  
> [!NOTE]
>  Указание `<issuerNameRegistry>` элемент как дочерний элемент элемента [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по-прежнему поддерживается для обеспечения обратной совместимости. Параметры на `<securityTokenHandlerConfiguration>` элемент переопределяют на `<identityConfiguration>` элемент.  
  
## <a name="example"></a>Пример  
 Следующий код XML показано, как указать поставщика конфигурации на основе реестра имен.  
  
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
