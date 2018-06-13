---
title: Метод ICorDebugStepper::Step
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2d282e27ec5068fa6fe7f58ba95458fdc219972
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419228"
---
# <a name="icordebugstepperstep-method"></a>Метод ICorDebugStepper::Step
Принуждает ICorDebugStepper выполнить один шаг через содержащую и, при необходимости, чтобы продолжить, при пошаговом выполнении функций, которые вызываются в потоке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `bStepIn`  
 [in] Значение `true` на шаг с заходом в функцию, которая вызывается в потоке. Значение `false` на шаг с обходом функции.  
  
## <a name="remarks"></a>Примечания  
 Этот шаг завершается, если общеязыковая среда выполнения выполняет следующую инструкцию управляемого кода в кадре средства пошагового. Если `Step` будет вызван для средства пошагового, который не находится в управляемого кода, шаг будет выполнен при выполнении потоком следующей инструкции управляемого кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
