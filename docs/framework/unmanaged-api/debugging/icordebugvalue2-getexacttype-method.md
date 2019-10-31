---
title: Метод ICorDebugValue2::GetExactType
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
ms.openlocfilehash: 441d225dadbbca09ab27c8ccd70debe32f4c12da
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140256"
---
# <a name="icordebugvalue2getexacttype-method"></a>Метод ICorDebugValue2::GetExactType
Возвращает указатель интерфейса на объект "ICorDebugType", представляющий <xref:System.Type> этого значения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppType`  
 заполняет Указатель на адрес объекта `ICorDebugType`, представляющий <xref:System.Type> значения, представленного этим объектом "ICorDebugValue2".  
  
## <a name="remarks"></a>Заметки  
 Метод `GetExactType` с учетом универсальных шаблонов заменяет методы [ICorDebugObjectValue:: coclass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) и [ICorDebugValue:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) , каждый из которых возвращает сведения о типе значения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
