---
title: Метод ICorDebugProcess5::EnumerateHeap
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeap
helpviewer_keywords:
- EnumerateHeap method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeap method [.NET Framework debugging]
ms.assetid: b0192104-6073-4089-a4df-dc29ee033074
topic_type:
- apiref
ms.openlocfilehash: c8cfc9cdf6580a002f6ac15080012a9e8c63be20
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129648"
---
# <a name="icordebugprocess5enumerateheap-method"></a>Метод ICorDebugProcess5::EnumerateHeap
Возвращает перечислитель для объектов в управляемой куче.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppObject`  
 заполняет Указатель на адрес объекта интерфейса [икордебугхеапенум](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) , который является перечислителем для объектов, находящихся в управляемой куче.  
  
## <a name="remarks"></a>Заметки  
 Перед вызовом метода `ICorDebugProcess5::EnumerateHeap` необходимо вызвать метод [метод ICorDebugProcess5:: GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) и проверить значение поля `areGCStructuresValid` возвращенного объекта [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) , чтобы убедиться, что куча сборки мусора в ее Текущее состояние является перечислимым. Кроме того, `ICorDebugProcess5::EnumerateHeap` возвращает `E_FAIL`, если во время существования процесса присоединяется слишком рано, до выделения памяти для управляемой кучи.  
  
 Объект интерфейса [икордебугхеапенум](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) является стандартным перечислителем, производным от интерфейса ICorDebugEnum, который позволяет перечислять объекты [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) . Этот метод заполняет объект коллекции [икордебугхеапенум](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) экземплярами [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) , предоставляющими сведения обо всех объектах. Коллекция может также включать экземпляры [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) , предоставляющие сведения об объектах, которые не находятся в корне ни в одном объекте, но еще не были собраны сборщиком мусора.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
