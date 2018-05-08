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
ms.openlocfilehash: dc4e51ec60c7526f36bbe4909bec91a527e0862c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a>Метод ICorDebugStepper::SetUnmappedStopMask
Задает значение, которое указывает тип несопоставимого кода, в котором выполнение будет остановлено.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `mask`  
 [in] Значение перечисления CorDebugUnmappedStop, которое указывает тип несопоставимого кода, в котором отладчик остановится выполнения.  
  
 Значение по умолчанию — STOP_OTHER_UNMAPPED. Значение по умолчанию STOP_UNMANAGED допустимо только при отладке взаимодействия.  
  
## <a name="remarks"></a>Примечания  
 Когда отладчик обнаруживает компиляции just-in-time (JIT), в которой отсутствует сопоставление в промежуточный язык Microsoft (MSIL), он прерывает выполнение, если установлен флаг, указывающий, что тип несопоставимого кода; в противном случае проверка прозрачно продолжается.  
  
 Если отладчик не использует средство организации пошагового режима для входа в метод, затем он не будет обходить обязательно неуправляемого кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
