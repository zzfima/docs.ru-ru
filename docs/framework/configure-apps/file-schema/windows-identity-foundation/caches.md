---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 5ad75ae18772d6e7c724f2cbf40c1e3083d5c345
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941969"
---
# <a name="caches"></a>\<> кэшей
Регистрирует кэши, используемые для маркеров сеансов и определения воспроизведения маркеров.  
  
 \<> System. identityModel  
\<identityConfiguration >  
\<> кэшей  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствуют  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<sessionSecurityTokenCache >](sessionsecuritytokencache.md)|Регистрирует кэш для токенов сеанса с помощью службы или коллекции обработчиков маркеров безопасности.|  
|[\<tokenReplayCache >](tokenreplaycache.md)|Регистрирует кэш воспроизведения токенов с помощью службы или коллекции обработчиков маркеров безопасности.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<identityConfiguration >](identityconfiguration.md)|Задает параметры удостоверений уровня службы.|  
|[\<Секурититокенхандлерконфигуратион >](securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.|  
  
## <a name="remarks"></a>Примечания  
 Элемент можно указать на уровне службы `<identityConfiguration>` в элементе или на уровне коллекции `<securityTokenHandlerConfiguration>` обработчика маркеров безопасности под элементом. `<caches>` Параметры коллекции обработчиков маркеров переопределяют указанные в службе.  
  
 `<caches>` Элемент представлен<xref:System.IdentityModel.Configuration.IdentityModelCachesElement> классом. Настроенные кэши представлены <xref:System.IdentityModel.Configuration.IdentityModelCaches> классом.  
  
## <a name="example"></a>Пример  
 В следующем коде XML показана конфигурация пользовательского кэша для хранения маркеров безопасности сеанса (<xref:System.IdentityModel.Tokens.SessionSecurityToken>). Конфигурация берется из `ClaimsAwareWebFarm` примера.  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
