---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: cebfc2f3598f32f233db6039dfe82076d2ffce46
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221708"
---
# <a name="trustedissuers"></a>\<trustedIssuers>
Настраивает список доверенных издателей сертификатов, используемых реестр имен издателей на основе конфигурации (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers >  
\<securityTokenHandlerConfiguration>  
\<issuerNameRegistry>  
\<trustedIssuers>  
  
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
  
|Элемент|Описание|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|Добавляет сертификат в коллекцию доверенных издателей. Сертификат указывается с помощью `thumbprint` атрибута. Этот атрибут является обязательным и должен содержать формы в кодировке ASN.1 отпечатка сертификата. `name` Атрибут является необязательным и может использоваться для указания понятное имя для сертификата.|  
|`<clear>`|Очищает все сертификаты из коллекции доверенных издателей.|  
|`<remove thumbprint=xs:string>`|Удаляет сертификат из коллекции доверенных издателей. Сертификат указывается с помощью `thumbprint` атрибута. Атрибут обязателен.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<issuerNameRegistry>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Настраивает реестр имен издателей. **Внимание!**  `type` Атрибут `<issuerNameRegistry>` должен ссылаться элемент <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса для `<trustedIssuers>` элемент был допустимым.|  
  
## <a name="remarks"></a>Примечания  
 Windows Identity Foundation (WIF) обеспечивает единую реализацию <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класс по умолчанию, <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса. Конфигурация реестр имен издателей ведет список доверенных издателей, загруженный из конфигурации. Список связывает каждое имя издателя с сертификатом X.509, который необходим для проверки подписи токенов, создаваемых издателем. Список доверенных издателей сертификатов, указанные в разделе `<trustedIssuers>` элемент. Каждый элемент в списке связывает имя мнемонический издателя с сертификатом X.509, который необходим для проверки подписи токенов, создаваемых этим издателем. Доверенные сертификаты указываются с помощью ASN.1 кодированной формы отпечатка сертификата и добавляются к коллекции с помощью `<add>` элемент. Вы можете удалить или удалить из списка издателей (сертификаты), с помощью `<clear>` и `<remove>` элементы.  
  
 `type` Атрибут `<issuerNameRegistry>` должен ссылаться элемент <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса для `<trustedIssuers>` элемент был допустимым.  
  
## <a name="example"></a>Пример  
 Следующий код XML показано, как указать поставщика конфигурации на основе реестра имен.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
