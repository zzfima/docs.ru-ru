---
title: Метод ICorDebugRegisterSet::GetRegisters
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
ms.openlocfilehash: 32e899622b9c649a08e3bca1b6645f70dcbcbb19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178545"
---
# <a name="icordebugregistersetgetregisters-method"></a>Метод ICorDebugRegisterSet::GetRegisters
Получает значение каждого регистра (на компьютере, который в настоящее время является исполнителем кода), которое указывается битной маской.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `mask`  
 (в) Битная маска, которая определяет, какие значения регистра должны быть извлечены. Каждый бит соответствует регистру. Если немного настроено на один, значение регистра извлекается; в противном случае значение регистра не извлекается.  
  
 `regCount`  
 (в) Количество значений регистра, которые необходимо получить.  
  
 `regBuffer`  
 (ваут) Массив объектов, `CORDB_REGISTER` каждый из которых получает значение регистра.  
  
## <a name="remarks"></a>Remarks  
 Размер массива должен быть равен количеству битов, установленных на один в битной маске. Параметр `regCount` определяет количество элементов в буфере, которые будут получать значения регистра. Если `regCount` значение слишком мало для числа регистров, указанных в маске, более высокие пронумерованные регистры будут усечены из набора. Если `regCount` значение слишком велико, `regBuffer` неиспользованные элементы будут неизменены.  
  
 Если битовая маска определяет регистр, который `GetRegisters` недоступен, возвращает неопределенное значение для этого регистра.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugRegisterSet](icordebugregisterset-interface.md)
- [Интерфейс ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
