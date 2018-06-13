---
title: Метод ICorProfilerInfo4::GetFunctionFromIP2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetFunctionFromIP2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2
helpviewer_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2 method [.NET Framework profiling]
- GetFunctionFromIP2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 46ff70f4-13e9-40a0-802a-0a40abcfc6a0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c4fe3eec4940b57001b7734c581076388f8ba0c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456990"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a>Метод ICorProfilerInfo4::GetFunctionFromIP2
Сопоставляет указатель инструкции управляемого кода JIT-компилятора-версии функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ip`  
 [in] Указатель инструкций в управляемом коде.  
  
 `pFunctionId`  
 [out] Идентификатор функции  
  
 `pReJitId`  
 [out] Идентификатор версии JIT-компилятора функции.  
  
## <a name="remarks"></a>Примечания  
 `GetFunctionFromIP2` Аналогично `GetFunctionFromIP`, за исключением того, что он получает Идентификатором JIT-компилятора, а не идентификатор функции, функции, которая содержит указанный IP-адрес.  
  
> [!NOTE]
>  `GetFunctionFromIP2` можно запустить сбор мусора, тогда как `GetFunctionFromIP` не будет.  Дополнительные сведения см. в разделе [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
