---
title: Метод ICorDebugManagedCallback2::FunctionRemapOpportunity
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc900ca20ac87ddecfd8f7adf0894af21ca5d2f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a>Метод ICorDebugManagedCallback2::FunctionRemapOpportunity
Уведомляет отладчик о том, что выполнение кода достигнет точки последовательности в более старой версии редактируемой функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pAppDomain`  
 [in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий измененную функцию.  
  
 `pThread`  
 [in] Указатель на объект ICorDebugThread, представляющий поток, на котором была обнаружена точка останова преобразования.  
  
 `pOldFunction`  
 [in] Указатель на объект ICorDebugFunction, представляющий версию функции, которая в настоящее время выполняется в потоке.  
  
 `pNewFunction`  
 [in] Указатель на объект ICorDebugFunction, представляющий последнюю версию функции.  
  
 `oldILOffset`  
 [in] Смещение указателя инструкций в старой версии функции Microsoft промежуточного языка MSIL.  
  
## <a name="remarks"></a>Примечания  
 Этот обратный вызов дает отладчику возможность выполнить повторное сопоставление указателя инструкций местом в новой версии указанной функции, вызвав [ICorDebugILFrame2::RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) метод. Если отладчик не был вызван `RemapFunction` перед вызовом [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) метода, среда выполнения будет выполняться старый код и формируют другой `FunctionRemapOpportunity` обратного вызова в следующей точке последовательности.  
  
 Этот обратный вызов будет вызываться для каждого кадра, выполняющего более старым заданной функции, пока отладчик возвращает значение S_OK.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
