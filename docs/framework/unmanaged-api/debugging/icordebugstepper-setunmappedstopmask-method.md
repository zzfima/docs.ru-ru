---
title: Метод ICorDebugStepper::SetUnmappedStopMask
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetUnmappedStopMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0a273c54559e8e297e09740ba9c770ce12d72d1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760583"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a>Метод ICorDebugStepper::SetUnmappedStopMask
Задает значение, указывающее тип кода, в котором выполнение будет остановлено.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `mask`  
 [in] Значение, указывающее тип кода, в котором отладчик остановит выполнение перечисления CorDebugUnmappedStop.  
  
 Значение по умолчанию — STOP_OTHER_UNMAPPED. Значение по умолчанию STOP_UNMANAGED допустим только для отладки взаимодействия.  
  
## <a name="remarks"></a>Примечания  
 Когда отладчик обнаруживает компиляции just-in-time (JIT), который не имеет соответствующего сопоставления промежуточного языка Майкрософт (MSIL), он прерывает выполнение, если установлен флаг, указывающий типа неуправляемого кода; в противном случае проверка прозрачно продолжается.  
  
 Если отладчик не использует средство организации пошагового режима для входа в метод, то он не будет обход обязательно неуправляемого кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
