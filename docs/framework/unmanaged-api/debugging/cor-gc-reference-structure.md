---
title: "Структура COR_GC_REFERENCE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_REFERENCE
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_GC_REFERENCE
helpviewer_keywords: COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a86604febb7641eef147608e564a27883fdc4bec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
  
|Член|Описание:|  
|------------|-----------------|  
|`domain`|Указатель на домен приложения, к которому принадлежит объект или дескриптора. Его значение может быть `null`.|  
|`location`|ICorDebugValue или ICorDebugReferenceValue-интерфейс, соответствующий объект, который будет собрана сборщиком мусора.|  
|`type`|Объект [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) значение перечисления, указывающее, откуда корня. Дополнительные сведения см. в разделе "Примечания".|  
|`extraData`|Дополнительные данные об объекте для сбора мусора. Эта информация зависит от источника объекта, как указано в `type` поле. Дополнительные сведения см. в разделе "Примечания".|  
  
## <a name="remarks"></a>Примечания  
 `type` Поле является [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) значение перечисления, указывающее, откуда ссылка. Определенный `COR_GC_REFERENCE` значение, может отражать следующие виды управляемых объектов:  
  
-   Объекты из всех управляемых стеков (`CorGCReferenceType.CorReferenceStack`). Сюда относятся активных ссылок в управляемом коде, а также объекты, созданные средой CLR.  
  
-   Объекты из таблицы дескрипторов (`CorGCReferenceType.CorHandle*`). Сюда входят строгих ссылок (`HNDTYPE_STRONG` и `HNDTYPE_REFCOUNT`) и статические переменные в модуле.  
  
-   Объекты из очереди метода завершения (`CorGCReferenceType.CorReferenceFinalizer`). Очереди метода завершения корневых объектов до выполнения метода завершения.  
  
 `extraData` Поле содержит дополнительные данные в зависимости от источника (или типов) ссылки. Доступны следующие значения:  
  
-   `DependentSource`. Если `type` — `CorGCREferenceType.CorHandleStrongDependent`, это поле является объект, если в активном состоянии, корней объект, который будет собрана сборщиком мусора во `COR_GC_REFERENCE.Location`.  
  
-   `RefCount`. Если `type` — `CorGCREferenceType.CorHandleStrongRefCount`, это поле является дескриптор счетчика ссылок.  
  
-   `Size`. Если `type` — `CorGCREferenceType.CorHandleStrongSizedByref`, это поле является последний размер дерева объектов, для которой сборщик мусора рассчитана корни объекта. Обратите внимание, что этот расчет не обязательно в актуальном состоянии.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
