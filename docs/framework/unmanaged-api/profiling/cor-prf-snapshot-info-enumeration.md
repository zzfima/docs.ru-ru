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
ms.openlocfilehash: 97bf3e69a8ea155d53479ba6f61988e56e3bd396
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867028"
---
# <a name="cor_prf_snapshot_info-enumeration"></a>Перечисление COR_PRF_SNAPSHOT_INFO
Указывает объем данных, которые необходимо передать обратно с помощью моментального снимка стека при каждом вызове функции [стаккснапшоткаллбакк](stacksnapshotcallback-function.md) профилировщика.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a>Участники  
  
|Участники|Описание|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|Указывает, что значения должны передаваться для всех `StackSnapshotCallback` параметров, кроме параметра `context`.|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|Указывает, что значения должны передаваться для всех параметров `StackSnapshotCallback`, включая параметр `context`.|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|Указывает, что будет использоваться более простой и альтернативный алгоритм анализа стека.|  
  
## <a name="remarks"></a>Заметки  
 Значения, предоставляемые перечислением `COR_PRF_SNAPSHOT_INFO`, передаются в качестве параметров в метод [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Метод DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)
- [Перечисления профилирования](profiling-enumerations.md)
