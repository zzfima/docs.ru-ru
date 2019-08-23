---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 5747a4cfa93118dd41292904b168bbef02fec415
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944081"
---
# <a name="tokenreplaycache"></a>\<tokenReplayCache >
Регистрирует кэш воспроизведения токенов с помощью службы или коллекции обработчиков маркеров безопасности.  
  
 \<> System. identityModel  
\<identityConfiguration >  
\<> кэшей  
\<tokenReplayCache >  
  
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
|type|Тип, производный от <xref:System.IdentityModel.Tokens.TokenReplayCache> класса. Дополнительные сведения о том, как указать пользовательский `type`параметр, см. в разделе [ссылки на пользовательские типы].
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> кэшей](caches.md)|Регистрирует кэши, используемые службой или коллекцией обработчиков маркеров безопасности.|  
  
## <a name="remarks"></a>Примечания  
 Кэш воспроизведения токенов используется для обнаружения воспроизводимых токенов. Обнаружение воспроизведения токенов включено [ \<элементом токенреплайдетектион >](tokenreplaydetection.md) , который также указывает максимальный срок действия токенов.  
  
## <a name="example"></a>Пример  
 В следующем коде XML показана конфигурация пользовательского кэша для обнаружения воспроизводимых токенов.  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<Токенреплайдетектион >](tokenreplaydetection.md)
