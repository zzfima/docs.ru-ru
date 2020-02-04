---
title: Перечисление COR_PRF_GC_ROOT_KIND
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_KIND
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_KIND
helpviewer_keywords:
- COR_PRF_GC_ROOT_KIND enumeration [.NET Framework profiling]
ms.assetid: b9fb1c03-417f-41d4-aed4-02cb4ade8def
topic_type:
- apiref
ms.openlocfilehash: bff45e6f6f57b95d07ac5073cb70020818cce000
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867169"
---
# <a name="cor_prf_gc_root_kind-enumeration"></a>Перечисление COR_PRF_GC_ROOT_KIND
Указывает тип корневого элемента сборки мусора, предоставляемый обратным вызовом [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|Корень — это переменная в стеке.|  
|`COR_PRF_GC_ROOT_FINALIZER`|Корень — это запись в очереди метода завершения.|  
|`COR_PRF_GC_ROOT_HANDLE`|Корень является обработчиком сборки мусора.|  
|`COR_PRF_GC_ROOT_OTHER`|Тип корня не указан.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления профилирования](profiling-enumerations.md)
