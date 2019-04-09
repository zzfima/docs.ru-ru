---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 1567c669b5e682a7a771d7bedc95a8effa474e36
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113390"
---
# <a name="tokenreplaycache"></a>\<tokenReplayCache>
Регистрирует кэш повторного использования токенов службы или коллекцию обработчиков токенов безопасности.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<caches>  
\<tokenReplayCache>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|type|Тип, который является производным от <xref:System.IdentityModel.Tokens.TokenReplayCache> класса. Дополнительные сведения о том, как задать пользовательский `type`, см. в разделе [ссылки на пользовательские типы].
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<caches>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Регистрирует кэши, используемые службы или коллекцию обработчиков токенов безопасности.|  
  
## <a name="remarks"></a>Примечания  
 Кэш повторного использования токенов используется для обнаружения переигранных токенов. Обнаружение воспроизведения токенов включено по [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) элемент, который также указывает максимальный срок действия маркеров.  
  
## <a name="example"></a>Пример  
 Следующий код XML показана конфигурация пользовательского кэша за обнаружение повторно используемых токенов.  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
