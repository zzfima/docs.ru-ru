---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: 209e702da80f2569f2b6c068f50f1af4489157f6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251967"
---
# <a name="issuernameregistry"></a>\<issuerNameRegistry >
Настраивает реестр имен издателя, используемый обработчиками в коллекции обработчиков маркеров.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Секурититокенхандлерконфигуратион >** ](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerNameRegistry >**  
  
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
|type|Тип, производный от <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса. Дополнительные сведения о том, как указать пользовательский `type`параметр, см. в разделе [ссылки на пользовательские типы].|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Трустедиссуерс >](trustedissuers.md)|Если атрибут указывает реестр имен издателя на основе конфигурации <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> (класс), [ \<](trustedissuers.md) необходимо указать элемент > трустедиссуерс. `type` Элемент > `<add>` `<clear>`трустедиссуерс может принимать элементы, или `<remove>` в качестве дочерних элементов. [ \<](trustedissuers.md)|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Секурититокенхандлерконфигуратион >](securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.|  
  
## <a name="remarks"></a>Примечания  
 Все маркеры издателя проверяются с помощью реестра имени издателя. Это объект, производный от <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса. Реестр имен издателей используется для связывания назначенного имени с криптографическим материалом, необходимым для проверки подписей маркеров, созданных соответствующим издателем. В реестре имен издателей хранится список издателей, которым доверяет приложение проверяющей стороны (RP). Тип реестра имени издателя указывается с помощью `type` атрибута. `<issuerNameRegistry>` Элемент может иметь один или несколько дочерних элементов, которые предоставляют конфигурацию для указанного типа. Вы предоставляете логику, которая обрабатывает эти дочерние элементы <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> , переопределяя метод.  
  
 WIF предоставляет один тип реестра имени поставщика из поля, <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класс. Этот класс использует набор сертификатов доверенных издателей, указанных в конфигурации. Для этого требуется дочерний элемент `<trustedIssuers>`конфигурации, в котором настроена Коллекция сертификатов доверенных издателей. Доверенные сертификаты указываются с помощью формы отпечатка сертификата в кодировке ASN. 1, которые добавляются или удаляются из `<add>`коллекции `<clear>`с помощью `<remove>` элементов, или.  
  
 `<issuerNameRegistry>` Элемент представлен<xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> классом.  
  
> [!NOTE]
> Указание элемента в качестве дочернего элемента [ \<элемента > identityConfiguration](identityconfiguration.md) является устаревшим, но по-прежнему поддерживается для обратной совместимости. `<issuerNameRegistry>` Параметры элемента переопределяют их `<identityConfiguration>` для элемента. `<securityTokenHandlerConfiguration>`  
  
## <a name="example"></a>Пример  
 В следующем коде XML показано, как указать реестр имен поставщиков на основе конфигурации.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
