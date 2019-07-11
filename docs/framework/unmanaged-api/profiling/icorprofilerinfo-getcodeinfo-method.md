---
title: Метод ICorProfilerInfo::GetCodeInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCodeInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCodeInfo
helpviewer_keywords:
- GetCodeInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetCodeInfo method [.NET Framework profiling]
ms.assetid: 90140b0f-a926-4a7e-b6fa-23e05f703cce
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2cc587edf763a352501a0d9097bdab2c54658d98
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762845"
---
# <a name="icorprofilerinfogetcodeinfo-method"></a>Метод ICorProfilerInfo::GetCodeInfo
Получает экстент машинного кода, связанного с указанным идентификатором функции.  
  
 Этот метод устарел. Используйте [ICorProfilerInfo2::GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) метод вместо этого.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCodeInfo(  
    [in]  FunctionID functionId,  
    [out] LPCBYTE    *pStart,  
    [out] ULONG      *pcSize);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionId`  
 [in] Идентификатор функции, с которым связан машинный код.  
  
 `pStart`  
 [out] Указатель на массив байтов, составляющих машинный код функции.  
  
 `pcSize`  
 [out] Указатель на целое число, задающее размер машинного кода в байтах.  
  
## <a name="remarks"></a>Примечания  
 Для оптимизации производительности среда выполнения в .NET Framework версии 2.0 разделяет предварительно скомпилированный машинный код функции на несколько областей. Следовательно, метод `GetCodeInfo` является устаревшим в .NET Framework 2.0, так как он не может обработать экстент машинного кода функции. Профилировщики следует переключить на использование более универсального метода `ICorProfilerInfo2::GetCodeInfo2`.  
  
 Эта функция использует буферы, выделенные вызывающим объектом.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** 1.0  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
