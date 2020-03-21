---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152571"
---
# <a name="securitytokenhandlerconfiguration"></a>\<securityTokenhandlerConfiguration>
Обеспечивает конфигурацию для сбора обработчиков токенов.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityМодель>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<идентичностьНастройка>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenhandlerConfiguration>**  
  
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
  
|attribute|Описание|  
|---------------|-----------------|  
|saveBootstrapКонтекст|Определяет, следует ли включать токены bootstrap в токен сеанса. Значение также может быть установлено на коллекции `saveBootstrapContext` обработчика маркеров, установив атрибут на элементе [ \<конфигурации>.](identityconfiguration.md) Значение, установленное в коллекции обработчика токенов, переопределяет значение, установленное в службе.|  
|maximumClockSkew|A, <xref:System.TimeSpan> который определяет максимально допустимые перекосы часов. Контролирует максимально допустимые перекосы часов при выполнении операций, чувствительных к времени, таких как проверка времени истечения сеанса входе. По умолчанию 5 минут, "00:05:00". Для получения дополнительной информации о том, как указать <xref:System.TimeSpan> значения, см. [Timespan Values](../windows-workflow-foundation/index.md) Максимальное перекос часов также может быть установлен `maximumClockSkew` на уровне обслуживания, установив атрибут на [ \<элементе конфигурации>.](identityconfiguration.md) Значение, установленное в коллекции обработчика токенов, переопределяет значение, установленное в службе.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<аудиторияУрис>](audienceuris.md)|Определяет набор УРИ, которые являются приемлемыми идентификаторами этой полагающейся стороны. Необязательный параметр.|  
|[\<кэши>](caches.md)|Регистрирует кэши, используемые для маркеров сеанса и обнаружения воспроизведения токенов. Может быть указан на уровне обслуживания или в коллекции обработчика маркеров безопасности. Необязательный параметр.|  
|[\<сертификатВалиста>](certificatevalidation.md)|Контролирует настройки, которые обработчики маркеров используют для проверки сертификатов. Может быть указан на уровне обслуживания или в коллекции обработчика маркеров безопасности. Эти параметры переопределяются, если определенный обработчик настроен с собственным валидатором. Необязательный параметр.|  
|[\<>эмитентаNameRegistry](issuernameregistry.md)|Настраивает реестр имен эмитента, который используется обработчиками в коллекции обработчиков токенов. Необязательный параметр.|  
|[\<issuerTokenResolver>](issuertokenresolver.md)|Регистрирует токен-решателя эмитента, который используется обработчиками в коллекции обработчиков токенов. Разрешители маркеров эмитента используются для разрешения маркера подписи на входящих токенах и сообщениях. Необязательный параметр.|  
|[\<serviceTokenResolver>](servicetokenresolver.md)|Регистрирует разрешителер маркеров службы, используемый обработчиками в коллекции обработчиков токенов. Разрешители токенов службы используются для разрешения маркера шифрования на входящих токенах и сообщениях. Необязательный параметр.|  
|[\<токенReplayDetection>](tokenreplaydetection.md)|Позволяет обнаружить маркеры и определяет время истечения срока действия токенов. Может быть указан на уровне обслуживания или в коллекции обработчика маркеров безопасности. Необязательный параметр.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|Определяет набор обработчиков маркеров безопасности, зарегистрированных в конечной точке.|  
  
## <a name="remarks"></a>Remarks  
 В этом разделе приведены <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> значения свойств для объекта. Настройки, настроенные в этом разделе, переопределяют настройки, настроенные на службу. Некоторые из этих параметров, в свою очередь, могут быть перекрыты настройками, которые указаны при добавлении обработчика в коллекцию обработчика маркеров безопасности.  
  
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
