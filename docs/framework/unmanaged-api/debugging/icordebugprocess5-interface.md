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
ms.openlocfilehash: 263124db75abdc058d26ffb606a13fc711aed8bf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792301"
---
# <a name="icordebugprocess5-interface"></a>Интерфейс ICorDebugProcess5
Расширяет интерфейс ICorDebugProcess для поддержки доступа к управляемой куче, предоставляет сведения о сборке мусора управляемых объектов и определяет, загружает ли отладчик изображения из локального кэша образов в машинном код.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnableNGenPolicy](icordebugprocess5-enablengenpolicy-method.md)|Задает значение, определяющее, как приложение загружает образы в машинном кодах при выполнении в управляемом отладчике.|  
|[Метод EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md)|Возвращает перечислитель для всех объектов, которые должны быть собраны в процессе сборки мусора.|  
|[Метод EnumerateHandles](icordebugprocess5-enumeratehandles-method.md)|Возвращает перечислитель для дескрипторов объектов в процессе.|  
|[Метод EnumerateHeap](icordebugprocess5-enumerateheap-method.md)|Возвращает перечислитель для объектов в управляемой куче.|  
|[Метод EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md)|Возвращает перечислитель для регионов управляемой кучи.|  
|[Метод GetArrayLayout](icordebugprocess5-getarraylayout-method.md)|Возвращает сведения о макете массива в памяти.|  
|[Метод GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md)|Возвращает указатель на структуру [COR_HEAPINFO](cor-heapinfo-structure.md) , содержащую сведения об объектах, которые должны быть собраны сборщиком мусора в управляемой куче.|  
|[Метод GetObject](icordebugprocess5-getobject-method.md)|Возвращает указатель на объект в управляемой куче.|  
|[Метод GetTypeFields](icordebugprocess5-gettypefields-method.md)|Возвращает указатель на массив, содержащий сведения о поле для типа на основе его идентификатора типа.|  
|[Метод GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md)|Возвращает объект типа, предоставляющий сведения об объекте на основе его идентификаторов типов.|  
|[Метод GetTypeID](icordebugprocess5-gettypeid-method.md)|Возвращает идентификатор типа для объекта по указанному адресу.|  
|[Метод GetTypeLayout](icordebugprocess5-gettypelayout-method.md)|Возвращает сведения о макете объекта в памяти на основе его идентификатора типа.|  
  
## <a name="remarks"></a>Заметки  
 Этот интерфейс логически расширяет интерфейсы ICorDebugProcess, ICorDebugProcess2 и [ICorDebugProcess3](icordebugprocess3-interface.md) .  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленный вызов на другом компьютере или другом процессе.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
