---
title: Метод ICorProfilerInfo::GetILFunctionBodyAllocator
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
ms.openlocfilehash: 5fe472c4a0053ec9e37d7d61ffde5cf21d65dd2f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863521"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a>Метод ICorProfilerInfo::GetILFunctionBodyAllocator
Возвращает интерфейс, предоставляющий метод для выделения памяти, используемой для перекачки тела метода в коде на языке MSIL.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleId`  
 окне Идентификатор модуля, в котором находится метод.  
  
 `ppMalloc`  
 заполняет Указатель на интерфейс [IMethodMalloc](imethodmalloc-interface.md) , предоставляющий метод для выделения памяти.  
  
## <a name="remarks"></a>Заметки  
 Тело метода в коде MSIL должен располагаться как относительный виртуальный адрес (RVA) относительно загруженного модуля. Это означает, что он следует за модулем в пределах 4 ГБ. Чтобы упростить средство для замены тела метода, метод `GetILFunctionBodyAllocator` гарантирует выделение памяти в пределах этого диапазона.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
