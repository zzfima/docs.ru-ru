---
title: Метод ICorProfilerThreadEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Skip method [.NET Framework profiling]
ms.assetid: acb8b029-4a96-4ed7-ae3c-310204e5ceea
topic_type:
- apiref
ms.openlocfilehash: b08a501f7d55fbb193afd8c297ca7725348dac76
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860934"
---
# <a name="icorprofilerthreadenumskip-method"></a>Метод ICorProfilerThreadEnum::Skip
Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `celt`  
 окне Число пропущенных элементов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|элементы `celt` пропущены.|  
|S_FALSE|Пропущено менее `celt` элементов, что означает, что больше нет элементов.|  
  
## <a name="remarks"></a>Заметки  
 Новая позиции курсора перечислителя — (Текущая позиции) + `celt`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md)
- [Интерфейсы профилирования](profiling-interfaces.md)
