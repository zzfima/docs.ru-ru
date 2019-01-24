---
title: Метод ICorProfilerInfo::SetEnterLeaveFunctionHooks
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5d5ad57c3a5523494ce0384e665764bc02f679e3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547427"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a>Метод ICorProfilerInfo::SetEnterLeaveFunctionHooks
Задает реализуемые профилировщиком функции, должен быть вызван в «enter», «проверить» и «tailcall» обработчиков управляемых функций.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pFuncEnter`  
 [in] Указатель на реализацию для использования в качестве [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) обратного вызова.  
  
 `pFuncLeave`  
 [in] Указатель на реализацию для использования в качестве [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) обратного вызова.  
  
 `pFuncTailcall`  
 [in] Указатель на реализацию для использования в качестве [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) обратного вызова.  
  
## <a name="remarks"></a>Примечания  
 В .NET Framework версии 1.0 каждого указателя функции может иметь значение null, чтобы отключить этот соответствующий обратный вызов.  
  
 Одновременно может быть активной только один набор обратных вызовов. Таким образом Если профилировщик вызывает оба `SetEnterLeaveFunctionHooks` и [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), затем `SetEnterLeaveFunctionHooks2` имеет более высокий приоритет.  
  
 `SetEnterLeaveFunctionHooks` Метод может вызываться только из профилировщика [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) обратного вызова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
