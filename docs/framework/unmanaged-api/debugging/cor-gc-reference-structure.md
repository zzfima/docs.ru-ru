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
ms.openlocfilehash: cc0b67621f77c0741e0b63b84ab1794530d6280b
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274227"
---
# <a name="cor_gc_reference-structure"></a>Структура COR_GC_REFERENCE
Содержит сведения об объекте, в котором должна быть выполнена сборка мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
|`domain`|Указатель на домен приложения, которому принадлежит маркер или объект. Его значение может быть `null`.|  
|`location`|Интерфейс ICorDebugValue или ICorDebugReferenceValue, соответствующий объекту, который должен быть собран сборщиком мусора.|  
|`type`|Значение перечисления [CorGCReferenceType](corgcreferencetype-enumeration.md) , указывающее, откуда поступил корень. Дополнительные сведения см. в разделе "Примечания".|  
|`extraData`|Дополнительные данные об объекте, который должен быть собран сборщиком мусора. Эти сведения зависят от источника объекта, как указано в `type` поле. Дополнительные сведения см. в разделе "Примечания".|  
  
## <a name="remarks"></a>Примечания  
 Поле `type` является значением перечисления [CorGCReferenceType](corgcreferencetype-enumeration.md), которое указывает, откуда поступила ссылка. Конкретное `COR_GC_REFERENCE` значение может отражать любой из следующих видов управляемых объектов:  
  
- Объекты из всех управляемых стеков (`CorGCReferenceType.CorReferenceStack`). Сюда входят динамические ссылки в управляемом коде, а также объекты, созданные средой CLR.  
  
- Объекты из таблицы Handle (`CorGCReferenceType.CorHandle*`). Это включает в себя строгие `HNDTYPE_REFCOUNT`ссылки (`HNDTYPE_STRONG` и) и статические переменные в модуле.  
  
- Объекты из очереди метода завершения (`CorGCReferenceType.CorReferenceFinalizer`). Очередь метода завершения помещает объекты в корни до запуска метода завершения.  
  
 `extraData` Поле содержит дополнительные данные в зависимости от источника (или типа) ссылки. Доступны следующие значения:  
  
- `DependentSource`. Если имеет `type` `CorGCREferenceType.CorHandleStrongDependent`значение, то это поле является объектом, в котором в случае со сроком существования объект, который должен `COR_GC_REFERENCE.Location`быть собран в мусор, находится в корне.  
  
- `RefCount`. Если значение `type` равно `CorGCREferenceType.CorHandleStrongRefCount`, это поле представляет собой счетчик ссылок для маркера.  
  
- `Size`. Если значение `type` равно `CorGCREferenceType.CorHandleStrongSizedByref`, это поле является последним размером дерева объектов, для которого сборщик мусора вычисляет корни объекта. Обратите внимание, что это вычисление не обязательно в актуальном состоянии.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
