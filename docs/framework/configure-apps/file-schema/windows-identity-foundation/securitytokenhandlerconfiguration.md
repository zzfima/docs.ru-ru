---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 168bdc4fbf640b201ebc61462d04727c23f838f2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a>&lt;securityTokenHandlerConfiguration&gt;
Обеспечивает настройку для коллекцию обработчиков токенов.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<securityTokenHandlerConfiguration >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
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
|saveBootstrapContext|Указывает, следует ли включать в токен сеанса начальной загрузки маркеры. Значение также может быть задана для коллекции обработчика токенов, задав `saveBootstrapContext` атрибут [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемента. Значение, заданное в коллекцию обработчиков токенов переопределяет значение, заданное для службы.|  
|maximumClockSkew|Объект <xref:System.TimeSpan> , указывающее максимально допустимое время отклонения. Определяет максимально допустимое время отклонения при выполнении операций, зависящих от времени, например для проверки истечения срока действия сеанса входа в систему. Значение по умолчанию — 5 минут «00: 05:00». Дополнительные сведения о способах указания <xref:System.TimeSpan> значения, в разделе [значения Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md). Также можно задать максимальную расфазировку синхронизирующих импульсов на уровне службы, задав `maximumClockSkew` атрибут [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемента. Значение, заданное в коллекцию обработчиков токенов переопределяет значение, заданное для службы.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<audienceUris >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|Задает набор URI, допустимых идентификаторов этой проверяющей стороны. Необязательный.|  
|[\<кэширует >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Регистрирует кэши, используемый для маркеров сеансов и обнаружение воспроизведения токенов. Можно указать на уровне службы или в коллекцию обработчика токенов безопасности. Необязательный.|  
|[\<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Управляет параметрами обработчиков токенов, используемых для проверки сертификатов. Можно указать на уровне службы или в коллекцию обработчика токенов безопасности. Эти параметры переопределяются, если обработчик конкретного настроен собственный проверяющий элемент управления. Необязательный.|  
|[\<issuerNameRegistry >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Настройка реестра имя издателя, используемая обработчиков в коллекцию обработчиков токенов. Необязательный.|  
|[\<issuerTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|Регистрирует Сопоставитель токена издателя, используемая обработчиков в коллекцию обработчиков токенов. Распознавателю маркеров издателя используется для разрешения маркера подписи для входящих токенов и сообщения. Необязательный.|  
|[\<serviceTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|Регистрирует Сопоставитель токена службы, используемой обработчиков в коллекцию обработчиков токенов. Распознавателю маркеров службы используется для разрешения маркера шифрования для входящих токенов и сообщения. Необязательный.|  
|[\<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Включает обнаружение воспроизведения токенов и определяет время жизни токенов. Можно указать на уровне службы или в коллекцию обработчика токенов безопасности. Необязательный.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<securityTokenHandlers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Задает коллекцию обработчиков токенов безопасности, которые зарегистрированы с конечной точкой.|  
  
## <a name="remarks"></a>Примечания  
 В этом разделе содержатся значения свойств для <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> объекта. Параметры, настроенные в этом разделе переопределяют настройки на стороне службы. Некоторые из этих параметров можно переопределить в свою очередь, используются параметры, которые указаны при добавлении обработчик в коллекцию обработчиков токенов безопасности.  
  
## <a name="example"></a>Пример  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>   
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```
