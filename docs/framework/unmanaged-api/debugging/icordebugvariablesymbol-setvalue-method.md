---
title: Метод ICorDebugVariableSymbol::SetValue
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5436f56d3dcad7de3df2296485b0a36e5b3cfd79
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967967"
---
# <a name="icordebugvariablesymbolsetvalue-method"></a>Метод ICorDebugVariableSymbol::SetValue
Присваивает переменной значение массива байтов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetValue(  
   [in] ULONG32 offset,  
   [in] DWORD threadID,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [in, size_is(cbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `offset`  
 [in] Начальное смещение в переменной, с которого следует задавать значение. Этот параметр используется при записи в поля членов в объекте.  
  
 `threadID`  
 [in] Идентификатор потока, чей контекст должен быть обновлен в соответствии с новым значением.  
  
 `cbContext`  
 [in] Размер контекста потока в байтах.  
  
 `context`  
 [in] Контекст потока, используемый для записи значения.  
  
 `cbValue`  
 [in] Размер буфера `pValue` в байтах.  
  
 `pValue`  
 [in] Буфер, содержащий значение, которое требуется задать.  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
