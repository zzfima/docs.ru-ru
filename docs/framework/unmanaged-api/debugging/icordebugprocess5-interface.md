---
title: Интерфейс ICorDebugProcess5
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5
helpviewer_keywords:
- ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5904083be66d4bd6dc69729bebc28db8a800e77
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089242"
---
# <a name="icordebugprocess5-interface"></a>Интерфейс ICorDebugProcess5
Расширяет интерфейс ICorDebugProcess для поддержки доступа к управляемой куче, для предоставления сведений о сборке мусора управляемых объектов, и чтобы определить, является ли отладчик загружает изображения из кэша образов в машинном коде локального приложения.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnableNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|Задает значение, определяющее, каким образом приложение загружает образы в машинном коде во время работы под контролем управляемого отладчика.|  
|[Метод EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|Получает перечислитель для всех объектов, которые должны быть удалены сборщиком мусора в процессе.|  
|[Метод EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|Возвращает перечислитель для дескрипторов объектов в процессе.|  
|[Метод EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|Получает перечислитель для объектов в управляемой куче.|  
|[Метод EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|Возвращает перечислитель для областей управляемой кучи.|  
|[Метод GetArrayLayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|Получает сведения о структуре массива в памяти.|  
|[Метод GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|Возвращает указатель на [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) структуру, содержащую сведения об объектах, которые должны быть удалены сборщиком мусора в управляемой куче.|  
|[Метод GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|Получает указатель на объект в управляемой куче.|  
|[Метод GetTypeFields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|Возвращает указатель на массив, содержащий данные поля для типа, на основе его идентификатора типа.|  
|[Метод GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|Возвращает объект типа, предоставляющий сведения об объекте на основе его типа идентификаторов.|  
|[Метод GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|Получает идентификатор для объекта по указанному адресу.|  
|[Метод GetTypeLayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|Получает сведения о расположении объекта в памяти, на основе его идентификатора типа.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс расширяет логически ICorDebugProcess ICorDebugProcess2, и [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) интерфейсов.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы с другого компьютера или из другого процесса.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
