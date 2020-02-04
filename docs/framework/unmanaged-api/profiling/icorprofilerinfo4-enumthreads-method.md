---
title: Метод ICorProfilerInfo4::EnumThreads
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumThreads
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type:
- apiref
ms.openlocfilehash: 5bea1b75e94d8011d3582d4f07d36bbc7a560502
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862221"
---
# <a name="icorprofilerinfo4enumthreads-method"></a>Метод ICorProfilerInfo4::EnumThreads
Возвращает перечислитель, предоставляющий методы для последовательного прохода по коллекции всех управляемых потоков в процессе профилирования.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppEnum`  
 заполняет Указатель на интерфейс [икорпрофилерсреаденум](icorprofilerthreadenum-interface.md) .  
  
## <a name="remarks"></a>Заметки  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md)
- [Интерфейс ICorProfilerInfo4](icorprofilerinfo4-interface.md)
- [Интерфейсы профилирования](profiling-interfaces.md)
- [Профилирование](index.md)
