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
ms.openlocfilehash: da799b0d4f4e5e4b281445baa35d95f992ba0b63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987458"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a>Метод ICorDebugStepper::SetUnmappedStopMask
Задает значение, указывающее тип кода, в котором выполнение будет остановлено.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
