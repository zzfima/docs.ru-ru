---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: 003221ed4dc7f4ccf72d2e0d3a91265e13172813
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941958"
---
# <a name="audienceuris"></a>\<audienceUris >
Указывает набор универсальных кодов ресурса (URI), которые являются допустимыми идентификаторами проверяющей стороны (RP). Токены не принимаются, если для одного из допустимых URI аудитории не задана область действия.  
  
 \<> System. identityModel  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<Секурититокенхандлерконфигуратион >  
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
|режим|Значение <xref:System.IdentityModel.Selectors.AudienceUriMode> типа, указывающее, следует ли применять ограничение аудитории к входящему токену. Возможные значения: "всегда", "Never" и "Беареркэйонли". Значение по умолчанию — Always. Необязательный параметр.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`<add value=xs:string>`|Добавляет URI, указанный `value` атрибутом, в коллекцию audienceUris. Атрибут `value` является обязательным. В URI учитывается регистр.|  
|`<clear>`|Очищает коллекцию audienceUris. Все идентификаторы удаляются из коллекции.|  
|`<remove value=xs:string>`|Удаляет URI, указанный `value` атрибутом из коллекции audienceUris. Атрибут `value` является обязательным. В URI учитывается регистр.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Секурититокенхандлерконфигуратион >](securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию коллекция пуста; Используйте `<add>`элементы `<clear>`, и`<remove>` для изменения коллекции. <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>объекты <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> и используют значения в коллекции URI аудитории для настройки любых допустимых ограничений URI аудитории в <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> объектах.  
  
 `<audienceUris>` Элемент представлен<xref:System.IdentityModel.Configuration.AudienceUriElementCollection> классом. Отдельный URI, добавленный в коллекцию, представлен <xref:System.IdentityModel.Configuration.AudienceUriElement> классом.  
  
> [!NOTE]
> Использование `<audienceUris>` элемента в качестве дочернего элемента [ \<элемента > identityConfiguration](identityconfiguration.md) является устаревшим, но по-прежнему поддерживается для обратной совместимости. Параметры элемента переопределяют их `<identityConfiguration>` для элемента. `<securityTokenHandlerConfiguration>`  
  
## <a name="example"></a>Пример  
 В следующем коде XML показано, как настроить допустимые URI аудитории для приложения. В этом примере настраивается один универсальный код ресурса (URI). Маркеры, областью которых является этот URI, будут приняты, все остальные будут отклонены.  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
