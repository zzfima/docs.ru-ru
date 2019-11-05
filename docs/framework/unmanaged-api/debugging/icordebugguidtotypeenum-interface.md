---
title: Интерфейс ICorDebugGuidToTypeEnum
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum
helpviewer_keywords:
- ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: aa32b12b-05fc-4ea8-a904-adae25034269
topic_type:
- apiref
ms.openlocfilehash: da921644c4d967efb0d88060ada0332c5eb63965
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138534"
---
# <a name="icordebugguidtotypeenum-interface"></a>Интерфейс ICorDebugGuidToTypeEnum
Предоставляет перечислитель, который определяет сопоставление между набором идентификаторов GUID и соответствующими типами, которые представлены экземплярами ICorDebugType. Этот интерфейс наследует методы от интерфейса ICorDebugEnum.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[ICorDebugGuidToTypeEnum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|Возвращает указанное число экземпляров [кордебуггуидтотипемаппинг](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) , которые сопоставляют идентификаторы GUID со сведениями о типе.|  
  
## <a name="remarks"></a>Заметки  
 Объект интерфейса `ICorDebugGuidToTypeEnum` можно извлечь, вызвав метод [ICorDebugAppDomain3:: GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) . Отладчик может вызвать [следующий](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) метод этого интерфейса для получения объектов [кордебуггуидтотипемаппинг](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) , представляющих сопоставления управляемых представлений типов Среда выполнения Windows, загруженных в домен приложения, используемый для вызова метода [ Метод ICorDebugAppDomain3:: GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** среда выполнения Windows  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
