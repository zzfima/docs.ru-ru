---
title: Метод ICorProfilerObjectEnum::Next
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Next
helpviewer_keywords:
- Next method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Next method [.NET Framework profiling]
ms.assetid: b420433c-5ebe-4986-bba1-97902e6db819
topic_type:
- apiref
ms.openlocfilehash: 0c833416cca965f2655266152c5bdf5f11624d14
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861142"
---
# <a name="icorprofilerobjectenumnext-method"></a>Метод ICorProfilerObjectEnum::Next
Возвращает указанное количество смежных объектов из последовательной коллекции объектов, начиная с текущей позиции перечислителя в последовательности.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `celt`  
 [in] Количество объектов, которые должны быть получены.  
  
 `objects`  
 заполняет Массив значений `ObjectID`, каждый из которых представляет извлеченный объект.  
  
 `pceltFetched`  
 [out] Указатель на число элементов, фактически извлеченных в массив `objects`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md)
