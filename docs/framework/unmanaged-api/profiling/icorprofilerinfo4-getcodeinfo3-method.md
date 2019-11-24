---
title: Метод ICorProfilerInfo4::GetCodeInfo3
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetCodeInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetCodeInfo3
helpviewer_keywords:
- GetCodeInfo3 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetCodeInfo3 method [.NET Framework profiling]
ms.assetid: bb8c105e-4d9a-4684-8c05-ed6909cc1b8c
topic_type:
- apiref
ms.openlocfilehash: d29145a9c224a064cf9210c56c8617d99f7690ba
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443065"
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a>Метод ICorProfilerInfo4::GetCodeInfo3
Получает экстенты машинного кода, связанного с перекомпилированной с помощью JIT-компилятора версией указанной функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionID`  
 [in] Идентификатор функции, с которым связан машинный код.  
  
 `reJitId`  
 [in] Идентификатор функции, перекомпилированной с помощью JIT-компилятора.  
  
 `cCodeInfos`  
 [in] Размер массива `codeInfos`.  
  
 `pcCodeInfos`  
 [out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.  
  
 `codeInfos`  
 [out] Буфер, предоставляемый вызывающим объектом. После возврата метода он содержит массив структур `COR_PRF_CODE_INFO`, каждая из которых описывает блок машинного кода.  
  
## <a name="remarks"></a>Заметки  
 The `GetCodeInfo3` method is similar to [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), except that it will get the JIT-recompiled ID of the function that contains the specified IP address.  
  
> [!NOTE]
> `GetCodeInfo3` can trigger a garbage collection, whereas [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) will not. For more information, see the [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.  
  
 Расширения сортируются в порядке возрастания смещения общих промежуточного языка (CIL).  
  
 After `GetCodeInfo3` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures. Для этого сравните значение параметра `cCodeInfos` со значением параметра `cchName`. If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo3` again.  
  
 Кроме того, сначала можно вызвать метод `GetCodeInfo3` с буфером `codeInfos` нулевой длины для получения правильного размера буфера. You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo3` again.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)
- [Интерфейс ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
