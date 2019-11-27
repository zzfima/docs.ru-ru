---
title: Перечисление COR_PRF_SNAPSHOT_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_SNAPSHOT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SNAPSHOT_INFO
helpviewer_keywords:
- COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type:
- apiref
ms.openlocfilehash: 6ade4f7877e39a8307a36f3a3268f79e8b4d44fd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427267"
---
# <a name="cor_prf_snapshot_info-enumeration"></a>Перечисление COR_PRF_SNAPSHOT_INFO
Указывает объем данных, которые необходимо передать обратно с помощью моментального снимка стека при каждом вызове функции [стаккснапшоткаллбакк](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) профилировщика.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a>Члены  
  
|Члены|Описание|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|Указывает, что значения должны передаваться для всех `StackSnapshotCallback` параметров, кроме параметра `context`.|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|Указывает, что значения должны передаваться для всех параметров `StackSnapshotCallback`, включая параметр `context`.|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|Указывает, что будет использоваться более простой и альтернативный алгоритм анализа стека.|  
  
## <a name="remarks"></a>Примечания  
 Значения, предоставляемые перечислением `COR_PRF_SNAPSHOT_INFO`, передаются в качестве параметров в метод [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [Перечисления профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
