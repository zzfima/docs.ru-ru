---
title: Перечисление COR_PRF_MISC
ms.date: 03/30/2017
api_name:
- COR_PRF_MISC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MISC
helpviewer_keywords:
- COR_PRF_MISC enumeration [.NET Framework profiling]
ms.assetid: 619bb5de-e309-48b6-a3af-32d935a0ff46
topic_type:
- apiref
ms.openlocfilehash: fe27c0fca6d38b4cff6cac2b9778cf2be68903a3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867130"
---
# <a name="cor_prf_misc-enumeration"></a>Перечисление COR_PRF_MISC
Содержит постоянные значения, которые указывают специальные идентификаторы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|Идентификатор по умолчанию, используемый [ICorProfilerInfo:: GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) для модуля, который еще не присоединен к сборке.|  
|`PROFILER_GLOBAL_CLASS`|Идентификатор класса по умолчанию для глобальных констант, которые не принадлежат классу.|  
|`PROFILER_GLOBAL_MODULE`|Идентификатор модуля по умолчанию для глобальных объектов, которые не принадлежат модулю.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления профилирования](profiling-enumerations.md)
