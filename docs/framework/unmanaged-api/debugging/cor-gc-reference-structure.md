---
title: Структура COR_GC_REFERENCE
ms.date: 03/30/2017
api_name:
- COR_GC_REFERENCE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_GC_REFERENCE
helpviewer_keywords:
- COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 848765a4ea9657020bd84e476f992ae69750dda9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617691"
---
# <a name="corgcreference-structure"></a>Структура COR_GC_REFERENCE
Содержит сведения об объекте, в котором должна быть выполнена сборка мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`domain`|Указатель на домен приложения, к которому принадлежит этот дескриптор или объект. Значение параметра может быть `null`.|  
|`location`|ICorDebugValue или ICorDebugReferenceValue-интерфейс, который соответствует объекту быть сборщиком мусора.|  
|`type`|Объект [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) значение перечисления, указывающее, откуда поступили корня. Дополнительные сведения см. в разделе "Примечания".|  
|`extraData`|Дополнительные данные об объекте, чтобы участвовать в сборе мусора. Эта информация зависит от источника объекта, как указано в `type` поля. Дополнительные сведения см. в разделе "Примечания".|  
  
## <a name="remarks"></a>Примечания  
 `type` Поле является [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) значение перечисления, указывающее, откуда поступили ссылки. Определенный `COR_GC_REFERENCE` значение может отражать любой из следующих типов управляемых объектов:  
  
- Объекты из всех управляемых стеков (`CorGCReferenceType.CorReferenceStack`). Сюда входят активных ссылок в управляемый код, а также объекты, созданные средой CLR.  
  
- Объекты из таблицы дескрипторов (`CorGCReferenceType.CorHandle*`). Сюда входят строгих ссылок (`HNDTYPE_STRONG` и `HNDTYPE_REFCOUNT`) и статические переменные в модуле.  
  
- Объекты из очереди метода завершения (`CorGCReferenceType.CorReferenceFinalizer`). Обслуживает очередь метода завершения корневых объектов, пока не будет запущен финализатор.  
  
 `extraData` Поле содержит дополнительные данные в зависимости от источника (или тип) ссылки. Доступны следующие значения:  
  
- `DependentSource`. Если `type` — `CorGCREferenceType.CorHandleStrongDependent`, это поле является объектом, который, если в активном состоянии, корней объекта сборщиком мусора в `COR_GC_REFERENCE.Location`.  
  
- `RefCount`. Если `type` является `CorGCREferenceType.CorHandleStrongRefCount`, это поле является счетчик ссылок дескриптора.  
  
- `Size`. Если `type` является `CorGCREferenceType.CorHandleStrongSizedByref`, это поле является последний размер дерева объектов, для которой сборщик мусора рассчитана корни объекта. Обратите внимание на то, что этот расчет не обязательно в актуальном состоянии.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
