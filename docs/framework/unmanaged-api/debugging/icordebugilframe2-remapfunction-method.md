---
title: Метод ICorDebugILFrame2::RemapFunction
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f03d8c993be1ac83ca84275bcb94f1bb3cdf884
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugilframe2remapfunction-method"></a>Метод ICorDebugILFrame2::RemapFunction
Перераспределяет отредактированную функцию путем указания нового смещения промежуточного языка MSIL Microsoft  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `newILOffset`  
 [in] Кадр стека следует поместить указатель инструкций новое смещение MSIL. Это значение должно являться точкой следования.  
  
 Это обязанность вызывающего, чтобы обеспечить правильность этого значения. Например не является допустимым, если оно находится за пределами функции смещение MSIL.  
  
## <a name="remarks"></a>Примечания  
 Когда функция фрейма была изменена, отладчик может вызвать `RemapFunction` метод для замены в последней версии функции фрейма, могут быть выполнены. Выполнение кода начинается с заданного смещения MSIL.  
  
> [!NOTE]
>  Вызов `RemapFunction`, таких как вызов [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), немедленно сделает недействительными все отладочные интерфейсы, связанные с генерацией трассировки стека для потока. Среди этих интерфейсов: [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame ICorDebugInternalFrame и ICorDebugNativeFrame.  
  
 `RemapFunction` Метод может вызываться только в контексте текущего кадра и только в одном из следующих случаев:  
  
-   После получения [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) обратный вызов, который еще не был продолжен.  
  
-   При остановке выполнения кода из-за [ICorDebugManagedCallback::EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) событий для этого кадра.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
