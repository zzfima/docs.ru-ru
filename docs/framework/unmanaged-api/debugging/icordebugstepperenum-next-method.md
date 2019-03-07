---
title: Метод ICorDebugStepperEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum::Next
helpviewer_keywords:
- Next method, ICorDebugStepperEnum interface [.NET Framework debugging]
- ICorDebugStepperEnum::Next method [.NET Framework debugging]
ms.assetid: d0ea0f30-e8d2-48b0-8477-e1a029ceb4dd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ac3165ab17eb1b4bc55a4bee4d2d2b467f8aefe
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494601"
---
# <a name="icordebugstepperenumnext-method"></a>Метод ICorDebugStepperEnum::Next
Получает указанное число экземпляров ICorDebugStepper из перечисления, начиная с текущей позиции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Next(  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugStepper *steppers[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `celt`  
 [in] Количество `ICorDebugStepper` извлекаемых экземпляров.  
  
 `steppers`  
 [out] Массив указателей, каждый из которых указывает `ICorDebugStepper` объекта.  
  
 `pceltFetched`  
 [out] Указатель на число `ICorDebugStepper` фактически возвращенных экземпляров. Это значение может иметь значение null Если `celt` — один.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
