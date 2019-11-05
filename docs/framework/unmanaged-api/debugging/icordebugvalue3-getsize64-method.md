---
title: Метод ICorDebugValue3::GetSize64
ms.date: 03/30/2017
api_name:
- ICorDebugValue3::GetSize64
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type:
- apiref
ms.openlocfilehash: 72a1b6fdc40f3169500d8cf3b3028315106ecc69
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140228"
---
# <a name="icordebugvalue3getsize64-method"></a>Метод ICorDebugValue3::GetSize64
Возвращает размер данного объекта [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) в байтах.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a>Параметры  
 псизе  
 заполняет Указатель на размер данного объекта в байтах.  
  
## <a name="remarks"></a>Заметки  
 Если этот тип значения является ссылочным, этот метод возвращает размер указателя, а не размер объекта.  
  
 Метод `ICorDebugValue3::GetSize` отличается от метода [ICorDebugValue:: resize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) в типе выходного параметра. В [ICorDebugValue::-size](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)выходной параметр является `ULONG32`; в `ICorDebugValue3::GetSize`это `ULONG64`. Это позволяет интерфейсу [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) сообщать размер массивов, ПРЕВЫШАЮЩИХ 2 ГБ.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
