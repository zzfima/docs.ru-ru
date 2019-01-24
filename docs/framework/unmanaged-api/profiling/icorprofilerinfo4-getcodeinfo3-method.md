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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 64382f0d405e84b2be78aac982b085fec35cb37b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675106"
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a>Метод ICorProfilerInfo4::GetCodeInfo3
Получает экстенты машинного кода, связанного с перекомпилированной с помощью JIT-компилятора версией указанной функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 `functionID`  
 [in] Идентификатор функции, с которым связан машинный код.  
  
 `reJitId`  
 [in] Идентификатор функции, перекомпилированной с помощью JIT-компилятора.  
  
 `cCodeInfos`  
 [in] Размер массива `codeInfos`.  
  
 `pcCodeInfos`  
 [out] Указатель на общее число [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) доступных структур.  
  
 `codeInfos`  
 [out] Буфер, предоставляемый вызывающим объектом. После возврата метода он содержит массив структур `COR_PRF_CODE_INFO`, каждая из которых описывает блок машинного кода.  
  
## <a name="remarks"></a>Примечания  
 `GetCodeInfo3` Метод аналогичен методу [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), за исключением того, что он будет получать перекомпиляции JIT идентификатор функции, которая содержит указанный IP-адрес.  
  
> [!NOTE]
>  `GetCodeInfo3` можно запустить сбор мусора, тогда как [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) не будет. Дополнительные сведения см. в разделе [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.  
  
 Расширения сортируются в порядке возрастания смещения общих промежуточного языка (CIL).  
  
 После `GetCodeInfo3` возвращает, необходимо убедиться, что `codeInfos` буфер был достаточно велик для размещения всех [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) структуры. Для этого сравните значение параметра `cCodeInfos` со значением параметра `cchName`. Если `cCodeInfos` деленное на размер [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) структура меньше, чем `pcCodeInfos`, Выделение большего `codeInfos` буфера, обновите `cCodeInfos` задав новый, больший размер и вызовите метод `GetCodeInfo3` еще раз.  
  
 Или же сначала можно вызвать метод `GetCodeInfo3` с буфером `codeInfos` нулевой длины для получения правильного размера буфера. Затем можно задать `codeInfos` размер равным значению, возвращенному в буфера `pcCodeInfos`, умноженному на размер [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) структуры и вызовите метод `GetCodeInfo3` еще раз.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Метод GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)
- [Интерфейс ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
