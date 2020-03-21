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
ms.openlocfilehash: e22269b76c230f702f4712298fddcd0df1fde50d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179318"
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
  
## <a name="members"></a>Члены  
  
|Участник|Описание|  
|------------|-----------------|  
|`domain`|Указатель на домен приложения, к которому принадлежит ручка или объект. Его значение `null`может быть .|  
|`location`|Либо ICorDebugValue или интерфейс ICorDebugReferenceValue, который соответствует объекту, который будет собран мусором.|  
|`type`|Значение [перечисления CorGCReferenceType,](corgcreferencetype-enumeration.md) которое указывает, откуда взялся корень. Дополнительные сведения см. в разделе «Примечания».|  
|`extraData`|Дополнительные данные об объекте, который должен быть собран мусором. Эта информация зависит от источника объекта, `type` как указано на поле. Дополнительные сведения см. в разделе «Примечания».|  
  
## <a name="remarks"></a>Remarks  
 Поле `type` представляет собой значение перечисления [CorGCReferenceType,](corgcreferencetype-enumeration.md) которое указывает, откуда пришла ссылка. Определенное `COR_GC_REFERENCE` значение может отражать любой из следующих видов управляемых объектов:  
  
- Объекты из всех`CorGCReferenceType.CorReferenceStack`управляемых стеков (). Это включает в себя живые ссылки в управляемом коде, а также объекты, созданные общим временем выполнения языка.  
  
- Объекты из таблицы рукоятки ().`CorGCReferenceType.CorHandle*` Это включает в`HNDTYPE_STRONG` себя `HNDTYPE_REFCOUNT`сильные ссылки (и ) и статические переменные в модуле.  
  
- Объекты из очереди`CorGCReferenceType.CorReferenceFinalizer`finalizer (). Очередь finalizer корни объектов до завершения.  
  
 Поле `extraData` содержит дополнительные данные в зависимости от источника (или типа) ссылки. Возможны следующие значения:  
  
- `DependentSource`. Если `type` это, `CorGCREferenceType.CorHandleStrongDependent`это поле является объектом, который, если жив, `COR_GC_REFERENCE.Location`корни объекта, который будет мусор собран на .  
  
- `RefCount`. Если `type` есть, `CorGCREferenceType.CorHandleStrongRefCount`это поле является эталоном ручки.  
  
- `Size`. Если `type` есть, `CorGCREferenceType.CorHandleStrongSizedByref`это поле является последним размером дерева объекта, для которого сборщик мусора вычислил корни объекта. Обратите внимание, что этот расчет не обязательно актуален.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры отладки](debugging-structures.md)
- [Отладки](index.md)
