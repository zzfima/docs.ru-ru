---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 1143717882652fc8a03947327b5f1ea89dde7373
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267434"
---
# <a name="servicetokenresolver"></a>\<serviceTokenResolver>
Регистрирует Сопоставитель токенов служб, используемый обработчиками в коллекцию обработчиков токенов. Сопоставитель токенов служб используется для разрешения токена шифрования на входящих токенов и сообщений.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers >  
\<securityTokenHandlerConfiguration>  
\<serviceTokenResolver>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
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
|type|Указывает тип Сопоставитель токенов служб. Либо <xref:System.IdentityModel.Selectors.SecurityTokenResolver> типом или типом, который является производным от <xref:System.IdentityModel.Selectors.SecurityTokenResolver> класса. Дополнительные сведения о способах указания `type` атрибут, см. в разделе [пользовательский тип ссылки]. Обязательный.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции безопасности обработчиков маркеров.|  
  
## <a name="remarks"></a>Примечания  
 Сопоставитель токенов служб можно использовать для разрешения токена шифрования на входящих токенов и сообщений. Он используется для извлечения ключа, который должен использоваться для расшифровки входящих маркеров. Необходимо указать `type` атрибута. Указанный тип может быть либо <xref:System.IdentityModel.Selectors.SecurityTokenResolver> или пользовательский тип, производный от <xref:System.IdentityModel.Selectors.SecurityTokenResolver> класса.  
  
 Некоторые обработчики маркеров позволяют пользователю указать параметры Сопоставитель токена службы в конфигурации. Параметры на отдельных обработчиков маркеров в переопределите указанных в коллекцию обработчиков токенов безопасности.  
  
> [!NOTE]
>  Указание `<serviceTokenResolver>` элемент как дочерний элемент элемента [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по-прежнему поддерживается для обеспечения обратной совместимости. Параметры на `<securityTokenHandlerConfiguration>` элемент переопределяют на `<identityConfiguration>` элемент.  
  
## <a name="example"></a>Пример  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
