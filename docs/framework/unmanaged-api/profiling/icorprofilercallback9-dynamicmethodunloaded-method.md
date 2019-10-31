---
title: 'ICorProfilerCallback9: метод:D Инамикмесодунлоадед'
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 05a788179ff40a6889ed613b5f8659dd3f8e066f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73196322"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a>ICorProfilerCallback9: метод:D Инамикмесодунлоадед
[Поддерживается в .NET Framework 4.7.2 и более поздних версиях]  
  
Уведомляет профилировщик каждый раз, когда динамический метод уничтожается сборщиком мусора и затем выгружается.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a>Параметры  
[входной] `functionId`  
Идентификатор функции в памяти, которая была собрана и выгружена сборщиком мусора.   

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [ICorProfilerCallback8. Динамикмесоджиткомпилатионстартед, метод](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8. Динамикмесоджиткомпилатионфинишед, метод](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [Интерфейс ICorProfilerCallback9](icorprofilercallback9-interface.md)
- [COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS](cor-prf-high-monitor-enumeration.md)
