---
title: Метод ICorDebugNativeFrame::SetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc442e0bcd8d392041284269e46821e0642d0891
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765885"
---
# <a name="icordebugnativeframesetip-method"></a>Метод ICorDebugNativeFrame::SetIP
Задает указатель инструкций в указанное расположение смещения в машинном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `nOffset`  
 [in] Расположение смещения в машинном коде.  
  
## <a name="remarks"></a>Примечания  
 Вызовы `SetIP` немедленно сделать недействительными все фреймы и цепочки для текущего потока. Если отладчику требуется сведения о кадре после вызова `SetIP`, он должен выполнить новую трассировку стека.  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) попытается сохранить кадр стека в допустимом состоянии. Тем не менее, даже если кадр находится в допустимом состоянии, как среды выполнения, по-прежнему может существовать проблемы, такие как неинициализированных локальных переменных и т. д. Вызывающий объект несет ответственность за обеспечение согласованности выполняемой программы.  
  
 На 64-разрядных платформах, нельзя перемещать указатель инструкций из `catch` или `finally` блока. Если `SetIP` вызывается для выполнения такого перемещения на 64-разрядной платформе, возвращается значение HRESULT, указывающее на сбой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
