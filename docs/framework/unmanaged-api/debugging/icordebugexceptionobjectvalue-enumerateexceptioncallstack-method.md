---
title: Метод ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type:
- apiref
ms.openlocfilehash: 57eb284bfe39ce92b2d6c03a2aeb4ae84d6aba91
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788666"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a>Метод ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
Возвращает перечислитель для стека вызовов, внедренного в объект исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  
 ппкаллстаккенум  
 заполняет Указатель на адрес объекта интерфейса [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) , который является перечислителем трассировки стека для управляемого объекта исключения.  
  
## <a name="remarks"></a>Заметки  
 Если сведения о стеке вызовов недоступны, метод возвращает `S_OK`, а [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) — допустимый перечислитель с длиной 0. Если методу не удается получить сведения о трассировке стека, возвращается значение `E_FAIL` и перечислитель не возвращается.  
  
 Объект [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) отвечает за декодирование данных трассировки стека из поля `_stackTrace` объекта исключения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugExceptionObjectValue](icordebugexceptionobjectvalue-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
