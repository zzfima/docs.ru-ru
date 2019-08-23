---
title: Метод ICorDebugVariableSymbol::GetValue
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b72b9dbeff6aa06a132dc7ec3ddd9477553c4c2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967996"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a>Метод ICorDebugVariableSymbol::GetValue
Возвращает значение переменной в виде массива байтов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetValue(  
   [in] ULONG32 offset,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [out] ULONG32 *pcbValue,  
   [out, size_is(cbValue), length_is(*pcbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `offset`  
 [in] Начальное смещение в переменной, с которого следует читать значение. Этот параметр используется при чтении полей членов в объекте.  
  
 `cbContext`  
 [in] Размер аргумента `context` в байтах.  
  
 `context`  
 [in] Контекст потока, используемый для чтения значения.  
  
 `cbValue`  
 [in] Размер буфера `pValue` в байтах.  
  
 `pcbValue`  
 [out] Число байтов, фактически записанных в буфер `pValue`.  
  
 `pValue`  
 [out] Массив байтов, содержащий значение переменной.  
  
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
