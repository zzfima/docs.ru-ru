---
title: Метод ICorProfilerModuleEnum::Next
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Next Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Next
helpviewer_keywords:
- ICorProfilerModuleEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: a3cea59d-7622-4323-897a-0a464c40f77f
topic_type:
- apiref
ms.openlocfilehash: 695a4386d9399a079df41f11f52a3185083784ed
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861389"
---
# <a name="icorprofilermoduleenumnext-method"></a>Метод ICorProfilerModuleEnum::Next
Возвращает заданное число смежных модулей из последовательной коллекции модулей начиная с текущей позиции перечислителя в последовательности.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    ModuleID ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
## <a name="parameters"></a>Параметры  
 `celt`  
 [in] Количество модулей для извлечения.  
  
 `ids`  
 [out] Массив значений `ModuleID`, каждое из которых представляет полученный модуль.  
  
 `pceltFetched`  
 [out] Указатель на число элементов, фактически извлеченных в массив `ids`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Возвращенные элементы `celt`.|  
|S_FALSE|Было возвращено элементов менее, чем `celt`, что указывает, что перечисление завершено.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md)
- [Интерфейсы профилирования](profiling-interfaces.md)
