---
title: '&lt;audienceUris&gt;'
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7415cb3f1792d2de566161ae6c348ef591b4a0c3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltaudienceurisgt"></a>&lt;audienceUris&gt;
Задает набор URI, допустимых идентификаторов проверяющей стороны (RP). Маркеры не будут приниматься, если только они относятся к одному из разрешенных URI аудитории.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<securityTokenHandlerConfiguration >  
\<audienceUris >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
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
|режим|<xref:System.IdentityModel.Selectors.AudienceUriMode> Значение, которое указывает, должно ли применяться ограничения аудитории входящий токен. Возможными значениями являются «Всегда», «Никогда» и «BearerKeyOnly». Значение по умолчанию — «Always». Необязательный.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`<add value=xs:string>`|Добавляет URI, указанный параметром `value` атрибут в коллекцию audienceUris. Атрибут `value` является обязательным. URI с учетом регистра.|  
|`<clear>`|Очищает коллекцию audienceUris. Все идентификаторы будут удалены из коллекции.|  
|`<remove value=xs:string>`|Удаляет URI, указанный параметром `value` атрибута из коллекции audienceUris. Атрибут `value` является обязательным. URI с учетом регистра.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Обеспечивает настройку для коллекции безопасности обработчиков маркеров.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию коллекция пуста; Используйте `<add>`, `<clear>`, и `<remove>` элементов для изменения коллекции. <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> и <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> объекты используют значения в коллекции URI аудитории для настройки любых разрешено аудитории ограничения URI в <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> объектов.  
  
 `<audienceUris>` Представлен <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> класса. Представляется отдельным URI, добавляемый в коллекцию <xref:System.IdentityModel.Configuration.AudienceUriElement> класса.  
  
> [!NOTE]
>  Использование `<audienceUris>` элемент как дочерний элемент элемента [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по-прежнему поддерживается для обеспечения обратной совместимости. Параметры на `<securityTokenHandlerConfiguration>` элемент переопределяют на `<identityConfiguration>` элемент.  
  
## <a name="example"></a>Пример  
 Следующий код XML показано, как настроить допустимый URI аудитории для приложения. В этом примере настраивается один URI. Принимаются только токены, заданные для данного универсального кода Ресурса, все остальные будут отклонены.  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
