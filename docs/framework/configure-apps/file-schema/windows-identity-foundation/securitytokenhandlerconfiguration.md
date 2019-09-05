---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 330e52bd73a8032e4073fe434c852e5bdf8e1d47
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251891"
---
# <a name="securitytokenhandlerconfiguration"></a>\<Секурититокенхандлерконфигуратион >
Предоставляет конфигурацию для коллекции обработчиков маркеров.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Секурититокенхандлерконфигуратион >**  
  
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
|савебутстрапконтекст|Указывает, следует ли включать в маркер сеанса начальные токены. Значение также может быть задано в коллекции обработчиков маркеров путем установки `saveBootstrapContext` атрибута [ \<для элемента identityConfiguration >](identityconfiguration.md) . Значение, заданное в коллекции обработчиков маркеров, переопределяет значение, заданное для службы.|  
|максимумклоккскев|Значение <xref:System.TimeSpan> типа, указывающее максимально допустимую отклонение в часах. Управляет максимально разрешенным отклонением по часам при выполнении операций с учетом времени, таких как проверка срока действия сеанса входа. Значение по умолчанию — 5 минут, "00:05:00". Дополнительные сведения об указании <xref:System.TimeSpan> значений см. в разделе [значения TimeSpan](../windows-workflow-foundation/index.md). Максимальная разница в часах может также быть задана на уровне службы путем задания `maximumClockSkew` атрибута [ \<для элемента identityConfiguration >](identityconfiguration.md) . Значение, заданное в коллекции обработчиков маркеров, переопределяет значение, заданное для службы.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<audienceUris >](audienceuris.md)|Указывает набор универсальных кодов ресурса (URI), которые являются допустимыми идентификаторами этой проверяющей стороны. Необязательный параметр.|  
|[\<> кэшей](caches.md)|Регистрирует кэши, используемые для маркеров сеансов и определения воспроизведения маркеров. Может указываться на уровне службы или в коллекции обработчиков маркеров безопасности. Необязательный параметр.|  
|[\<Цертификатевалидатион >](certificatevalidation.md)|Управляет параметрами, которые обработчики маркеров используют для проверки сертификатов. Может указываться на уровне службы или в коллекции обработчиков маркеров безопасности. Эти параметры переопределяются, если для определенного обработчика настроен собственный проверяющий элемент управления. Необязательный параметр.|  
|[\<issuerNameRegistry >](issuernameregistry.md)|Настраивает реестр имен издателя, используемый обработчиками в коллекции обработчиков маркеров. Необязательный параметр.|  
|[\<Иссуертокенресолвер >](issuertokenresolver.md)|Регистрирует сопоставитель маркеров издателя, используемый обработчиками в коллекции обработчиков маркеров. Сопоставитель токенов издателя используется для разрешения маркера подписывания входящих токенов и сообщений. Необязательный параметр.|  
|[\<Сервицетокенресолвер >](servicetokenresolver.md)|Регистрирует сопоставитель маркеров службы, используемый обработчиками в коллекции обработчиков маркеров. Сопоставитель токенов службы используется для разрешения маркера шифрования входящих токенов и сообщений. Необязательный параметр.|  
|[\<Токенреплайдетектион >](tokenreplaydetection.md)|Включает обнаружение воспроизведения маркеров и задает срок действия токенов. Может указываться на уровне службы или в коллекции обработчиков маркеров безопасности. Необязательный параметр.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<securityTokenHandlers >](securitytokenhandlers.md)|Указывает коллекцию обработчиков маркеров безопасности, зарегистрированных в конечной точке.|  
  
## <a name="remarks"></a>Примечания  
 В <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> этом разделе приводятся значения свойств для объекта. Параметры, настроенные в этом разделе, переопределяют настройки, настроенные в службе. Некоторые из этих параметров, в свою очередь, могут быть переопределены параметрами, заданными при добавлении обработчика в коллекцию обработчиков маркеров безопасности.  
  
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
