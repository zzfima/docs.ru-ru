---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: 556c444d5e48e27036c4b49338f6e70de7ef5c5d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750752"
---
# <a name="audienceuris"></a>\<audienceUris>
Задает набор URI, — это допустимые идентификаторы проверяющей стороны (RP). Маркеры не будет принят, если только они относятся к одному из разрешенных URI аудитории.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers >  
\<securityTokenHandlerConfiguration>  
\<audienceUris>  
  
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
|режим|<xref:System.IdentityModel.Selectors.AudienceUriMode> Значение, указывающее, должна ли применяться ограничение аудитории на входящий токен. Возможные значения: «Всегда», «Никогда» и «BearerKeyOnly». По умолчанию используется «Всегда». Необязательный параметр.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`<add value=xs:string>`|Добавляет URI, указанный параметром `value` атрибут в коллекцию audienceUris. Атрибут `value` является обязательным. URI с учетом регистра.|  
|`<clear>`|Очищает коллекцию audienceUris. Все идентификаторы будут удалены из коллекции.|  
|`<remove value=xs:string>`|Удаляет URI, указанный параметром `value` атрибут из коллекции audienceUris. Атрибут `value` является обязательным. URI с учетом регистра.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции безопасности обработчиков маркеров.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию коллекция пуста; Используйте `<add>`, `<clear>`, и `<remove>` элементы для изменения коллекции. <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> и <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> объектам используются значения в коллекцию URI аудитории для настройки любых допускается audience URI ограничения в <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> объектов.  
  
 `<audienceUris>` Элемент, представленный объектом <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> класса. Представлен отдельным URI, добавляемый в коллекцию <xref:System.IdentityModel.Configuration.AudienceUriElement> класса.  
  
> [!NOTE]
>  Использование `<audienceUris>` элемент как дочерний элемент элемента [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по-прежнему поддерживается для обеспечения обратной совместимости. Параметры на `<securityTokenHandlerConfiguration>` элемент переопределяют на `<identityConfiguration>` элемент.  
  
## <a name="example"></a>Пример  
 Следующий код XML показано, как настроить допустимые URI аудитории для приложения. В этом примере настраивается один URI. Токены, заданные для данного универсального кода Ресурса будут приняты, все остальные будут отклонены.  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
