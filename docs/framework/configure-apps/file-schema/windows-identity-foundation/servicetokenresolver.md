---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 69d34cb54c2236f178ac4291ed24a3f5b45db48e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923111"
---
# <a name="servicetokenresolver"></a>\<Сервицетокенресолвер >
Регистрирует сопоставитель маркеров службы, используемый обработчиками в коллекции обработчиков маркеров. Сопоставитель токенов службы используется для разрешения маркера шифрования входящих токенов и сообщений.  
  
 \<> System. identityModel  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<Секурититокенхандлерконфигуратион >  
\<Сервицетокенресолвер >  
  
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
|type|Указывает тип сопоставителя токенов службы. Либо тип, либо тип, производный <xref:System.IdentityModel.Selectors.SecurityTokenResolver> от класса. <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы]. Обязательный.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Секурититокенхандлерконфигуратион >](securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.|  
  
## <a name="remarks"></a>Примечания  
 Сопоставитель токенов службы можно использовать для разрешения маркера шифрования входящих токенов и сообщений. Он используется для получения ключа, который должен использоваться для расшифровки входящих токенов. Необходимо указать `type` атрибут. Указанный тип может быть либо <xref:System.IdentityModel.Selectors.SecurityTokenResolver> либо пользовательским типом, производным <xref:System.IdentityModel.Selectors.SecurityTokenResolver> от класса.  
  
 Некоторые обработчики маркеров позволяют задавать параметры сопоставителя токенов служб в конфигурации. Параметры отдельных обработчиков маркеров переопределяют те, которые указаны в коллекции обработчика маркеров безопасности.  
  
> [!NOTE]
> Указание элемента в качестве дочернего элемента [ \<элемента > identityConfiguration](identityconfiguration.md) является устаревшим, но по-прежнему поддерживается для обратной совместимости. `<serviceTokenResolver>` Параметры элемента переопределяют их `<identityConfiguration>` для элемента. `<securityTokenHandlerConfiguration>`  
  
## <a name="example"></a>Пример  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
