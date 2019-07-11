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
ms.openlocfilehash: bdcc2eccbb24a92643415db8e5d267033ac1ca0a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758747"
---
# <a name="icordebugilframe2remapfunction-method"></a>Метод ICorDebugILFrame2::RemapFunction
Перераспределяет отредактированную функцию, указав новое смещение промежуточного языка MSIL Microsoft  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `newILOffset`  
 [in] Кадр стека по которому должен быть помещен указатель инструкции новое смещение MSIL. Это значение должно являться точкой следования.  
  
 Это обязанность вызывающего, чтобы обеспечить правильность этого значения. Например смещение MSIL является недопустимым, если он находится за пределами функции.  
  
## <a name="remarks"></a>Примечания  
 Когда функция фрейма был изменен, то отладчик может вызвать `RemapFunction` замену в последней версии функции фрейма, поэтому он может выполняться методом. Выполнение кода начинается с заданного смещения MSIL.  
  
> [!NOTE]
>  Вызов `RemapFunction`, например вызов [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), немедленно сделает недействительными все интерфейсы отладки, которые связаны с генерацией трассировки стека для потока. Такие интерфейсы включают [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame ICorDebugInternalFrame и ICorDebugNativeFrame.  
  
 `RemapFunction` Метод может вызываться только в контексте текущего кадра и только в следующих случаях:  
  
- После получения [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) обратный вызов, который еще не был продолжен.  
  
- Когда выполнение кода остановлен из-за [ICorDebugManagedCallback::EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) событий для данного кадра.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
