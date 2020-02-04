---
title: Интерфейс ICorDebugObjectValue
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
ms.openlocfilehash: e104f8c522af2ee4cd42332b7459f4a2fd185511
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792690"
---
# <a name="icordebugobjectvalue-interface"></a>Интерфейс ICorDebugObjectValue

Подкласс "ICorDebugValue", представляющий значение, которое содержит объект.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetClass](icordebugobjectvalue-getclass-method.md)|Возвращает указатель интерфейса на <xref:System.Type> среды CLR объекта, на который ссылается этот `ICorDebugObjectValue`.|  
|[Метод GetContext](icordebugobjectvalue-getcontext-method.md)|Не реализовано.|  
|[Метод GetFieldValue](icordebugobjectvalue-getfieldvalue-method.md)|Возвращает указатель интерфейса на объект [ICorDebugValue](icordebugvalue-interface.md) , представляющий значение указанного поля указанного класса.|  
|[Метод GetManagedCopy](icordebugobjectvalue-getmanagedcopy-method.md)|Устаревшее. Не вызывайте этот метод.|  
|[Метод GetVirtualMethod](icordebugobjectvalue-getvirtualmethod-method.md)|Не реализовано.|  
|[Метод IsValueClass](icordebugobjectvalue-isvalueclass-method.md)|Возвращает значение, указывающее, является ли объект, на который ссылается данный `ICorDebugObjectValue`, типом значения.|  
|[Метод SetFromManagedCopy](icordebugobjectvalue-setfrommanagedcopy-method.md)|Устаревшее. Не вызывайте этот метод.|  
  
## <a name="remarks"></a>Заметки  
 `ICorDebugObjectValue` остается действительным до тех пор, пока отлаживаемый процесс не будет продолжен.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
