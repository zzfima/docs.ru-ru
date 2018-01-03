---
title: '&lt;trustedIssuers&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 26f3d4f0b272168083bed2bbe249532181a6db67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="lttrustedissuersgt"></a>&lt;trustedIssuers&gt;
Настраивает список доверенных издателей сертификатов, используемых реестр имен издателей на основе конфигурации (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<securityTokenHandlerConfiguration >  
\<issuerNameRegistry >  
\<trustedIssuers >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
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
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|Добавляет сертификат в коллекцию доверенных издателей. Сертификат указан с `thumbprint` атрибута. Этот атрибут является обязательным и должен содержать отпечаток сертификата в кодировке ASN.1 формы. `name` Атрибут является необязательным и может использоваться для указания понятное имя для сертификата.|  
|`<clear>`|Очищает все сертификаты из коллекции доверенных издателей.|  
|`<remove thumbprint=xs:string>`|Удаляет сертификат из коллекции доверенных издателей. Сертификат указан с `thumbprint` атрибута. Атрибут обязателен.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<issuerNameRegistry >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Настраивает реестр имен поставщиков. **Важно:** `type` атрибут `<issuerNameRegistry>` должен ссылаться на элемент <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса для `<trustedIssuers>` элемент был допустимым.|  
  
## <a name="remarks"></a>Примечания  
 Windows Identity Foundation (WIF) предоставляет одну реализацию <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класс готовые <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса. В системном реестре имя издателя ведет список доверенных издателей, загруженная из конфигурации. Список связывает имя каждого издателя с сертификатом X.509, который необходим для проверки подписи токенов, полученных поставщиком. Список доверенных издателей сертификатов, указанные в разделе `<trustedIssuers>` элемента. Каждый элемент в списке связывает имя издателя, назначенный с сертификатом X.509, который необходим для проверки подписи токенов, созданных этим издателем. Доверенных сертификатов задаются с помощью ASN.1 кодированной формы отпечатка сертификата и добавляются к коллекции с помощью `<add>` элемента. Вы можете удалить или удалить из списка издателей (сертификатов), с помощью `<clear>` и `<remove>` элементы.  
  
 `type` Атрибут `<issuerNameRegistry>` должен ссылаться на элемент <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса для `<trustedIssuers>` элемент был допустимым.  
  
## <a name="example"></a>Пример  
 Следующий код XML показано, как указать поставщика конфигурации на основе реестра имя.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
