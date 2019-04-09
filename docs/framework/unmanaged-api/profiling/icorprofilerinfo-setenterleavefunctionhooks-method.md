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
ms.openlocfilehash: a2d45e98f3e7b71375b14c43c4bff4929bc79494
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142536"
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
  
## <a name="parameters"></a>Параметры  
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
