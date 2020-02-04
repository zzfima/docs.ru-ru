---
title: Интерфейс ICorDebugHandleValue
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue
helpviewer_keywords:
- ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type:
- apiref
ms.openlocfilehash: 406468fc6e2b68e8c8e1dfbd0f0f18cce3f013ab
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794456"
---
# <a name="icordebughandlevalue-interface"></a>Интерфейс ICorDebugHandleValue

Подкласс ICorDebugReferenceValue, представляющий ссылочное значение, в котором отладчик создал маркер для сборки мусора.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Dispose](icordebughandlevalue-dispose-method.md)|Освобождает дескриптор, на который ссылается данный объект `ICorDebugHandleValue`, без явного освобождения указателя интерфейса.|  
|[Метод GetHandleType](icordebughandlevalue-gethandletype-method.md)|Возвращает значение Кордебугхандлетипе, описывающее тип маркера, на который ссылается этот `ICorDebugHandleValue`.|  
  
## <a name="remarks"></a>Заметки  
 Объект `ICorDebugReferenceValue` становится недействительным при прерывании выполнения отлаживаемого кода. `ICorDebugHandleValue` сохраняет свои ссылки с помощью разрывов и продолжений, пока он не будет явно освобожден.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
