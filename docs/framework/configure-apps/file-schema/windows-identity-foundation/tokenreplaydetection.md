---
title: '&lt;tokenReplayDetection&gt;'
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7f0cef2590bb301e6897aa4922454942ecdd0957
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="lttokenreplaydetectiongt"></a>&lt;tokenReplayDetection&gt;
Включает обнаружение воспроизведения токенов и определяет время жизни токенов.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<tokenReplayDetection >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a>Тип  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|enabled|Значение, указывающее, включено ли обнаружение воспроизведения токенов; «true», чтобы включить токен обнаружения воспроизведения.|  
|expirationPeriod|Объект <xref:System.TimeSpan> , указывающее максимальное количество времени, прежде чем элемент считается истек и удаляется из кэша.  Дополнительные сведения о способах указания <xref:System.TimeSpan> значения, в разделе [значения Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Указывает параметры уровня службы удостоверений.|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Обеспечивает настройку для коллекции безопасности обработчиков маркеров.|  
  
## <a name="remarks"></a>Примечания  
 A `<tokenReplayDetection>` элемент можно задать на уровне службы под `<identityConfiguration>` элемент, либо на уровне коллекции обработчик маркеров безопасности в разделе `<securityTokenHandlerConfiguration>` элемента. Параметры в коллекцию обработчика токенов переопределяют алгоритмам, заданным в службе.  
  
 Тип кэша воспроизведения токена определяется [ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) элемента.
