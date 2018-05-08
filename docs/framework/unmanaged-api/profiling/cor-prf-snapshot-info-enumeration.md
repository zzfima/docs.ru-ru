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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d6713a7f54f6a6d8dbf261ad45304e6ddbe24c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="corprfsnapshotinfo-enumeration"></a>Перечисление COR_PRF_SNAPSHOT_INFO
Указывает, какой объем данных для обратной передачи со снимком стека в каждом вызове функции профилировщика [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a>Участники  
  
|Участники|Описание|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|Указывает, что значения должны передаваться для всех `StackSnapshotCallback` параметров, за исключением `context` параметра.|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|Указывает, что значения должны передаваться для всех `StackSnapshotCallback` параметров, включая `context` параметра.|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|Указывает, что будет использоваться простой и альтернативный алгоритм прохода стека.|  
  
## <a name="remarks"></a>Примечания  
 Значения, предоставленные `COR_PRF_SNAPSHOT_INFO` перечисления передаются как параметры для [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Метод DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
 [Перечисления профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
