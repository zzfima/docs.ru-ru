---
title: Метод ICorDebugStepper::SetInterceptMask
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetInterceptMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type:
- apiref
ms.openlocfilehash: e88fa543eca39c14962f0dbbe8053829713401c8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137584"
---
# <a name="icordebugsteppersetinterceptmask-method"></a>Метод ICorDebugStepper::SetInterceptMask
Задает значение, указывающее типы кода, в который выполняется пошаговое выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `mask`  
 окне Сочетание значений перечисления CorDebugIntercept, определяющих типы кода.  
  
## <a name="remarks"></a>Заметки  
 Если задан бит для перехватчика, средство пошагового выполнения будет выполнено при обнаружении заданного типа перехвата кода. Если бит сброшен, перехват кода будет пропущен.  
  
 Метод `SetInterceptMask` может иметь непредвиденные взаимодействия с [ICorDebugStepper:: сетунмаппедстопмаск](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (от точки зрения пользователя). Например, если только видимая (невнутренняя) часть кода инициализации класса не имеет сведений о сопоставлении и STOP_NO_MAPPING_INFO не задана (см [. метод ICorDebugStepper:: сетунмаппедстопмаск](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) и кордебугунмаппедстоп перечисление), средство организации пошагового прохода по инициализации класса. По умолчанию будет использоваться только значение INTERCEPT_NONE перечисления `CorDebugIntercept`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
