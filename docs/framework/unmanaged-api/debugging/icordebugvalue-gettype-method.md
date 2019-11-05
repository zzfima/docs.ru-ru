---
title: Метод ICorDebugValue::GetType
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
ms.openlocfilehash: 284a74823b01305f8c6e025f70bb9209c8607b7b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137079"
---
# <a name="icordebugvaluegettype-method"></a>Метод ICorDebugValue::GetType
Возвращает тип примитива этого объекта "ICorDebugValue".  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pType`  
 заполняет Указатель на значение перечисления "Корелементтипе", которое указывает тип значения.  
  
## <a name="remarks"></a>Заметки  
 Если объект является сложным типом времени выполнения, этот тип можно исследовать с помощью соответствующих подклассов интерфейса `ICorDebugValue`. Например, "ICorDebugObjectValue", который наследует от `ICorDebugValue`, представляет сложный тип.  
  
 Методы `GetType` и [ICorDebugObjectValue:: coclass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) возвращают сведения о типе значения. Они заменяются методом [ICorDebugValue2:: GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) , поддерживающим универсальные шаблоны.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
