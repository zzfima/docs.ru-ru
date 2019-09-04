---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 50fc7194823fb0c5c426fb54ffd50b17c3714ed9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251759"
---
# <a name="trustedissuers"></a>\<Трустедиссуерс >
Настраивает список сертификатов доверенных издателей, используемых в реестре имен поставщиков на основе конфигурации<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>().  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Секурититокенхандлерконфигуратион >** ](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuerNameRegistry >** ](issuernameregistry.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Трустедиссуерс >**  
  
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
 Отсутствуют  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|Добавляет сертификат в коллекцию доверенных издателей. Сертификат указывается с помощью `thumbprint` атрибута. Этот атрибут является обязательным и должен содержать форму отпечатка сертификата в кодировке ASN. 1. `name` Атрибут является необязательным и может использоваться для указания понятного имени сертификата.|  
|`<clear>`|Удаляет все сертификаты из коллекции доверенных издателей.|  
|`<remove thumbprint=xs:string>`|Удаляет сертификат из коллекции доверенных издателей. Сертификат указывается с помощью `thumbprint` атрибута. Атрибут обязателен.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<issuerNameRegistry >](issuernameregistry.md)|Настраивает реестр имен издателя. **Важно!**  Атрибут элемента должен ссылаться на класс, чтобы элемент был допустимым. `<trustedIssuers>` <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> `type` `<issuerNameRegistry>`|  
  
## <a name="remarks"></a>Примечания  
 Windows Identity Foundation (WIF) предоставляет единую реализацию <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса из Box <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> , класса. В реестре имени издателя конфигурации хранится список доверенных издателей, которые загружаются из конфигурации. Список всех имен издателей связывается с сертификатом X. 509, который необходим для проверки подписи маркеров, созданных издателем. Список сертификатов доверенных издателей указывается в `<trustedIssuers>` элементе. Каждый элемент в списке связывает назначенное имя издателя с сертификатом X. 509, который необходим для проверки подписи маркеров, созданных этим издателем. Доверенные сертификаты указываются с помощью формы отпечатка сертификата в кодировке ASN. 1 и добавляются в коллекцию `<add>` с помощью элемента. Можно удалить или удалить издателей (сертификаты) из списка с помощью `<clear>` элементов и. `<remove>`  
  
 Атрибут элемента должен ссылаться на класс, чтобы элемент был допустимым. `<trustedIssuers>` <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> `type` `<issuerNameRegistry>`  
  
## <a name="example"></a>Пример  
 В следующем коде XML показано, как указать реестр имен поставщиков на основе конфигурации.  
  
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
