---
title: "&lt;audienceUris&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# &lt;audienceUris&gt;
Задает набор URI, допустимые идентификаторы доверяющей стороне \(RP\).  Если областью действия для одного допустимую аудиторию URIs маркеров не будет принят.  
  
## Синтаксис  
  
```  
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
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|mode|<xref:System.IdentityModel.Selectors.AudienceUriMode> Значение, которое определяет, применены ли ограничение аудитории для входящего маркера.  Возможные значения: «Всегда», «Никогда» и «BearerKeyOnly».  Значение по умолчанию — «Всегда».  Необязательный.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`<add value=xs:string>`|Добавляет URI, заданного параметром `value` audienceUris коллекцию атрибутов.  Атрибут `value` является обязательным.  URI с учетом регистра.|  
|`<clear>`|Очищает коллекцию audienceUris.  Все идентификаторы будут удалены из коллекции.|  
|`<remove value=xs:string>`|Удаляет URI, заданного параметром `value` атрибут из коллекции audienceUris.  Атрибут `value` является обязательным.  URI с учетом регистра.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Содержит настройки для коллекции безопасности обработчиков маркеров.|  
  
## Заметки  
 По умолчанию коллекция является пустой; Использование `<add>`, `<clear>`, и `<remove>` элементов для изменения коллекции.  <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>и <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> объектами Допустимы значения в аудитории URI коллекции для настройки любой аудитории ограничения URI в <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> объектов.  
  
 `<audienceUris>` Представленного элементом <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> класса.  Представляется отдельным URI, добавляются в коллекцию <xref:System.IdentityModel.Configuration.AudienceUriElement> класса.  
  
> [!NOTE]
>  Использование `<audienceUris>` элемент как дочерний элемент [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по\-прежнему поддерживается для обратной совместимости.  Параметры на `<securityTokenHandlerConfiguration>` элементов заменяют на `<identityConfiguration>` элемент.  
  
## Пример  
 Следующий XML показано, как настроить приемлемых аудиторию URIs для приложения.  В этом примере настраивает одного URI.  Маркеры масштаба для данного URI будет принята, все остальные будут отклонены.  
  
```  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```