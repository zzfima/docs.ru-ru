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
ms.openlocfilehash: 00c9939b25f395010f6ea5832b405c3e9928a223
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792030"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a>Метод ICorDebugRegisterSet2::GetRegistersAvailable
Возвращает массив байтов, предоставляющий битовую карту доступных регистров.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `numChunks`  
 [in] Размер массива `availableRegChunks`.  
  
 `availableRegChunks`  
 заполняет Массив байтов, каждый бит которого соответствует регистру. Если регистр доступен, устанавливается соответствующий бит регистра.  
  
## <a name="remarks"></a>Заметки  
 Значения перечисления CorDebugRegister указывают регистры различных микропроцессоров. Верхние пять битов каждого значения являются индексом в `availableRegChunks` массиве байтов. Младшие три бита каждого значения обозначают битовую точку в индексируемом байте. При указании `CorDebugRegister` значения, указывающего конкретный регистр, расположение регистра в маске определяется следующим образом:  
  
1. Извлеките индекс, необходимый для доступа к правильному байту в массиве `availableRegChunks`:  
  
     `CorDebugRegister` значение > > 3  
  
2. Извлечение битовой позиции в индексируемом байте, где нулевой бит является наименее значимым битом:  
  
     `CorDebugRegister` значение & 7  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
- [Интерфейс ICorDebugRegisterSet](icordebugregisterset-interface.md)
