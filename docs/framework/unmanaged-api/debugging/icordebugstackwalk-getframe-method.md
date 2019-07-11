---
title: Метод ICorDebugStackWalk::GetFrame
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetFrame
helpviewer_keywords:
- GetFrame method [.NET Framework debugging]
- ICorDebugStackWalk::GetFrame method [.NET Framework debugging]
ms.assetid: 4083b505-5b59-44fb-8c5d-129db6a96c10
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81c3eec9b33f51bd30cf8724eaf010d7cd0b6cd4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760929"
---
# <a name="icordebugstackwalkgetframe-method"></a>Метод ICorDebugStackWalk::GetFrame
Получает текущий кадр [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a>Параметры  
 `pFrame`  
 [in] Указатель на адрес объекта созданный кадр, который представляет текущий кадр стека.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Среда выполнения успешно возвращено текущего кадра.|  
|E_FAIL|Текущий кадр не возвращен.|  
|S_FALSE|Текущий кадр является кадром стека.|  
|E_INVALIDARG|Параметр `pFrame` имеет значение null.|  
|CORDBG_E_PAST_END_OF_STACK|Указатель кадра уже находится в конце стека; Таким образом может осуществляться без дополнительных кадров.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugStackWalk` Возвращает только фактические кадры стека. Используйте [ICorDebugThread3::GetActiveInternalFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) метод для возврата внутренних кадрах. (Внутренние кадры — это структуры данных, помещается в стек средой выполнения для хранения временных данных.)  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
