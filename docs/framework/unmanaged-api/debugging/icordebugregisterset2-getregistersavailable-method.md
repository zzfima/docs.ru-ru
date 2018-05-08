---
title: Метод ICorDebugRegisterSet2::GetRegistersAvailable
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3a9cdb49c1a44dbc68cd4b7ccf4d4781ce5c539
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugregisterset2getregistersavailable-method"></a>Метод ICorDebugRegisterSet2::GetRegistersAvailable
Возвращает массив байтов, предоставляющий растровое изображение доступных регистров.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `numChunks`  
 [in] Размер массива `availableRegChunks`.  
  
 `availableRegChunks`  
 [out] Массив байтов, из которых каждый бит соответствует регистру. Если регистр, соответствующий бит регистра устанавливается.  
  
## <a name="remarks"></a>Примечания  
 Значения перечисления CorDebugRegister указывают регистры различных микропроцессоров. Верхние пять бит каждое значение — это индекс в `availableRegChunks` массива байтов. Три младших битов каждого значения идентифицируют положение бита в индексируемом байте. Получает `CorDebugRegister` значение, которое указывает определенный регистр, положение регистра в маске определяется следующим образом:  
  
1.  Извлеките индекс, необходимые для доступа к правильно байта в `availableRegChunks` массива:  
  
     `CorDebugRegister` Значение >> 3  
  
2.  Извлеките позиция разряда в индексируемом байте, в котором нулевой бит является наименее значимым битом:  
  
     `CorDebugRegister` значение & 7  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [Интерфейс ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
