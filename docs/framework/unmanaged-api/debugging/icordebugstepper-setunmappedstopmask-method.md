---
title: "Метод ICorDebugStepper::SetUnmappedStopMask"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.SetUnmappedStopMask
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 163a26ff38d0a4bbae5710d6d841ea29682a8984
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
