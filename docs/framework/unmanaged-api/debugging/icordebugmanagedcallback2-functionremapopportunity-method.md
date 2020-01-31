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
ms.openlocfilehash: bc6543b46200dd611e13bdf55aabfabd8302e70a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793333"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a>Метод ICorDebugManagedCallback2::FunctionRemapOpportunity
Уведомляет отладчик о том, что выполнение кода достигло точки последовательности в более ранней версии измененной функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pAppDomain`  
 окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий измененную функцию.  
  
 `pThread`  
 окне Указатель на объект ICorDebugThread, представляющий поток, в котором была обнаружена точка останова сопоставления.  
  
 `pOldFunction`  
 окне Указатель на объект ICorDebugFunction, представляющий версию функции, которая в данный момент выполняется в потоке.  
  
 `pNewFunction`  
 окне Указатель на объект ICorDebugFunction, представляющий последнюю версию функции.  
  
 `oldILOffset`  
 окне Смещение указателя инструкции в старой версии функции на языке MSIL.  
  
## <a name="remarks"></a>Заметки  
 Этот обратный вызов дает отладчику возможность перенаправить указатель инструкции в соответствующую позицию в новой версии указанной функции, вызвав метод [ICorDebugILFrame2:: RemapFunction](icordebugilframe2-remapfunction-method.md) . Если отладчик не вызывает `RemapFunction` перед вызовом метода [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) , среда выполнения продолжит выполнение старого кода и запустит другой обратный вызов `FunctionRemapOpportunity` в следующей точке последовательности.  
  
 Этот обратный вызов будет вызываться для каждого кадра, который выполняет более старую версию данной функции до тех пор, пока отладчик не возвратит S_OK.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
