---
title: Метод ICorProfilerInfo3::EnumModules
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumModules Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumModules
helpviewer_keywords:
- ICorProfilerInfo3::EnumModules method [.NET Framework profiling]
- EnumModules method [.NET Framework profiling]
ms.assetid: 1bf00b42-69da-4019-91b3-bf88026e83fb
topic_type:
- apiref
ms.openlocfilehash: 626ecddae8ba91d1830d98210208f9fbee36f073
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868592"
---
# <a name="icorprofilerinfo3enummodules-method"></a>Метод ICorProfilerInfo3::EnumModules
Возвращает перечислитель, предоставляющий методы для последовательного перебора коллекции управляемых модулей, загруженных в приложение.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppEnum`  
 заполняет Указатель на интерфейс [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .  
  
## <a name="remarks"></a>Заметки  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md)
- [Интерфейс ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Интерфейсы профилирования](profiling-interfaces.md)
- [Профилирование](index.md)
