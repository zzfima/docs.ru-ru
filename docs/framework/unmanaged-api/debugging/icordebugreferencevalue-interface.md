---
title: Интерфейс ICorDebugReferenceValue
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
ms.openlocfilehash: 16d7b89ee441e8d634c36fb87185b3f2846860b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137712"
---
# <a name="icordebugreferencevalue-interface"></a>Интерфейс ICorDebugReferenceValue
Предоставляет методы, управляющие значением, которое является ссылкой на объект. (Т. е. Этот интерфейс предоставляет методы, управляющие указателем.) Этот интерфейс реализует "ICorDebugValue".  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Dereference](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|Возвращает объект, на который указывает ссылка.|  
|[Метод DereferenceStrong](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|Не реализовано. Не вызывайте этот метод.|  
|[Метод GetValue](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|Возвращает текущий адрес памяти объекта, на который указывает ссылка.|  
|[Метод IsNull](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|Возвращает значение, указывающее, является ли `ICorDebugReferenceValue` значением NULL, в этом случае `ICorDebugReferenceValue` не указывает на объект.|  
|[Метод SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|Задает текущий адрес памяти. Это значит, что этот метод задает `ICorDebugReferenceValue`, указывающий на объект.|  
  
## <a name="remarks"></a>Заметки  
 Среда CLR может выполнять сборку мусора для объектов при продолжении отлаживаемого процесса. Сборка мусора может перемещать объекты в памяти. `ICorDebugReferenceValue` будет взаимодействовать со сборкой мусора, чтобы ее сведения обновлялись после сборки мусора, или она будет неявной недействительной до сборки мусора.  
  
 После продолжения отлаживаемого процесса объект `ICorDebugReferenceValue` может быть неявно недействительным. Производный "ICorDebugHandleValue" не является недействительным до тех пор, пока он не будет явно освобожден или открыт.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
