---
title: Метод ICorDebugProcess6::DecodeEvent
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
ms.openlocfilehash: a0b77724a5a70461073d554a9794c5a904f6a363
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178584"
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
 (в) [РегистраторRecordFormat](cordebugrecordformat-enumeration.md) перечисляет, который определяет формат неуправляемого события отладки.  
  
 `dwFlags`  
 [входной] Битовое поле, которое зависит от целевой архитектуры и содержит дополнительные сведения о событии отладки. Для систем Windows он может быть участником пересчета [CorDebugDecodeEventFlagsWindows.](cordebugdecodeeventflagswindows-enumeration.md)  
  
 `dwThreadId`  
 [входной] Идентификатор операционной системы для потока, в котором возникло исключение.  
  
 `ppEvent`  
 (ваут) Указатель на адрес объекта [ICorDebugDebugEvent,](icordebugdebugevent-interface.md) представляющего декодированное управляемое событие отладки.  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugProcess6](icordebugprocess6-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
