---
title: '&lt;tokenReplayDetection&gt;'
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: bd2272cb83dc0183d5008cfa178e11783f51ca2d
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2018
ms.locfileid: "48261059"
---
# <a name="lttokenreplaydetectiongt"></a>&lt;tokenReplayDetection&gt;
Включает обнаружение воспроизведения токенов и определяет срок действия маркеров.  
  
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
|enabled|Значение, указывающее, включено ли обнаружение воспроизведения токенов; «true», чтобы включить маркер обнаружения воспроизведения.|  
|expirationPeriod|Объект <xref:System.TimeSpan> , указывающий максимальное количество времени, прежде чем элемент считается устаревшим и удаляется из кэша.  Дополнительные сведения о способах указания <xref:System.TimeSpan> значения, см. в разделе [значения Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Указывает параметры уровня службы идентификации.|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции безопасности обработчиков маркеров.|  
  
## <a name="remarks"></a>Примечания  
 Объект `<tokenReplayDetection>` на уровне службы может быть задан элемент `<identityConfiguration>` элемент или на уровне коллекции обработчиков токенов безопасности в разделе `<securityTokenHandlerConfiguration>` элемент. Переопределить параметры на коллекцию обработчиков токенов, теми, которые указаны в службе.  
  
 Тип кэша повторного использования токенов задается [ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) элемент.
