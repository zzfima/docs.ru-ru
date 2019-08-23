---
title: Метод ICorDebugProcess6::DecodeEvent
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f81c513447b7c63fb16ff20ae6f83c3e6ef359b1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964044"
---
# <a name="icordebugprocess6decodeevent-method"></a>Метод ICorDebugProcess6::DecodeEvent
Декодирует события управляемой отладки, которые были инкапсулированы в полезную нагрузку из событий отладки специально созданных собственных исключений.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,   
        [in] DWORD dwThreadId,   
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pRecord`  
 [входной] Указатель на массив байтов из события отладки собственного исключения, содержащий данные о событии управляемой отладки.  
  
 `countBytes`  
 [входной] Количество элементов в массиве байтов `pRecord`.  
  
 `format`  
 окне Элемент перечисления [кордебугрекордформат](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) , указывающий формат неуправляемого события отладки.  
  
 `dwFlags`  
 [входной] Битовое поле, которое зависит от целевой архитектуры и содержит дополнительные сведения о событии отладки. Для систем Windows он может быть членом перечисления [кордебугдекодивентфлагсвиндовс](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) .  
  
 `dwThreadId`  
 [входной] Идентификатор операционной системы для потока, в котором возникло исключение.  
  
 `ppEvent`  
 заполняет Указатель на адрес объекта [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) , который представляет декодированное управляемое событие отладки.  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
