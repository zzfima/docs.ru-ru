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
ms.openlocfilehash: 7ae06d825565faff70b0c8be2ccbee5228737e41
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791104"
---
# <a name="icordebugvalue3getsize64-method"></a>Метод ICorDebugValue3::GetSize64
Возвращает размер данного объекта [ICorDebugValue3](icordebugvalue3-interface.md) в байтах.  
  
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
  
 Метод `ICorDebugValue3::GetSize` отличается от метода [ICorDebugValue:: resize](icordebugvalue-getsize-method.md) в типе выходного параметра. В [ICorDebugValue::-size](icordebugvalue-getsize-method.md)выходной параметр является `ULONG32`; в `ICorDebugValue3::GetSize`это `ULONG64`. Это позволяет интерфейсу [ICorDebugValue3](icordebugvalue3-interface.md) сообщать размер массивов, ПРЕВЫШАЮЩИХ 2 ГБ.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugValue3](icordebugvalue3-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
