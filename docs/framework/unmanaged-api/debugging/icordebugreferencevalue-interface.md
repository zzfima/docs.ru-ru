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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67006603747abd89f1b635c065860dcbe1c47a29
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965646"
---
# <a name="icordebugreferencevalue-interface"></a>Интерфейс ICorDebugReferenceValue
Предоставляет методы, управляющие значением, которое является ссылкой на объект. (Т. е. Этот интерфейс предоставляет методы, управляющие указателем.) Этот интерфейс реализует "ICorDebugValue".  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Dereference](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|Возвращает объект, на который указывает ссылка.|  
|[Метод DereferenceStrong](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|Не реализовано. Не вызывайте этот метод.|  
|[Метод GetValue](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|Возвращает текущий адрес памяти объекта, на который указывает ссылка.|  
|[Метод IsNull](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|Возвращает значение, указывающее, `ICorDebugReferenceValue` является ли значение значением NULL, в этом случае, `ICorDebugReferenceValue` не указывает на объект.|  
|[Метод SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|Задает текущий адрес памяти. Это значит, что этот метод задает `ICorDebugReferenceValue` значение, которое указывает на объект.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR может выполнять сборку мусора для объектов при продолжении отлаживаемого процесса. Сборка мусора может перемещать объекты в памяти. `ICorDebugReferenceValue` Либо взаимодействуют со сборкой мусора, так что ее сведения обновляются после сборки мусора, или же она становится неявной до сборки мусора.  
  
 После продолжения отлаживаемого процесса объектможетбытьнеявнонедействительным.`ICorDebugReferenceValue` Производный "ICorDebugHandleValue" не является недействительным до тех пор, пока он не будет явно освобожден или открыт.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
