---
title: Метод ICorDebugStepper::IsActive
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type:
- apiref
ms.openlocfilehash: a242764710d92e81e8089bc2919734bfac4bcdb2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137567"
---
# <a name="icordebugstepperisactive-method"></a>Метод ICorDebugStepper::IsActive
Возвращает значение, указывающее, выполняется ли в данный момент шаг.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbActive`  
 заполняет Возвращает `true`, если средство Организации в данный момент исполняет шаг; в противном случае возвращает `false`.  
  
## <a name="remarks"></a>Заметки  
 Любое действие шага остается активным до тех пор, пока отладчик не получит вызов [ICorDebugManagedCallback:: StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) , который автоматически деактивирует средство Организации. Пошаговое руководство также может быть деактивировано преждевременно путем вызова [ICorDebugStepper::D еактивате](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) до достижения условия обратного вызова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
