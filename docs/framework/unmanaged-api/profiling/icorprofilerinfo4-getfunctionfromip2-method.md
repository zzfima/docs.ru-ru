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
ms.openlocfilehash: 8c133338ec0edac19f49d435df41e3081c486f51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948467"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a>Метод ICorProfilerInfo4::GetFunctionFromIP2
Сопоставляет указатель инструкции управляемого кода с JIT-повторно скомпилированной версией функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a>Параметры  
 `ip`  
 окне Указатель инструкции в управляемом коде.  
  
 `pFunctionId`  
 заполняет Идентификатор функции.  
  
 `pReJitId`  
 заполняет Удостоверение JIT-повторно скомпилированной версии функции.  
  
## <a name="remarks"></a>Примечания  
 `GetFunctionFromIP2`функция похожа `GetFunctionFromIP`на, за исключением того, что он получает JIT-перекомпилированный идентификатор вместо идентификатора функции функции, которая содержит указанный IP-адрес.  
  
> [!NOTE]
> `GetFunctionFromIP2`может запустить сборку мусора, тогда как `GetFunctionFromIP` это не будет.  Дополнительные сведения см. в разделе [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf. idl, CorProf. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
