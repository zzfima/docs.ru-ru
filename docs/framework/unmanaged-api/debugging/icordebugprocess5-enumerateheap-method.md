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
ms.openlocfilehash: 780f9eb0984e35c4487d770b5e7ff33917cf07ed
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792418"
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
 заполняет Указатель на адрес объекта интерфейса [икордебугхеапенум](icordebugheapenum-interface.md) , который является перечислителем для объектов, находящихся в управляемой куче.  
  
## <a name="remarks"></a>Заметки  
 Перед вызовом метода `ICorDebugProcess5::EnumerateHeap` необходимо вызвать метод [метод ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) и проверить значение поля `areGCStructuresValid` возвращаемого [COR_HEAPINFO](cor-heapinfo-structure.md) объекта, чтобы гарантировать, что куча сборки мусора в ее текущем состоянии является перечислимым. Кроме того, `ICorDebugProcess5::EnumerateHeap` возвращает `E_FAIL`, если во время существования процесса присоединяется слишком рано, до выделения памяти для управляемой кучи.  
  
 Объект интерфейса [икордебугхеапенум](icordebugheapenum-interface.md) является стандартным перечислителем, производным от интерфейса ICorDebugEnum, который позволяет перечислить [COR_HEAPOBJECTные](cor-heapobject-structure.md) объекты. Этот метод заполняет объект коллекции [икордебугхеапенум](icordebugheapenum-interface.md) экземплярами [COR_HEAPOBJECT](cor-heapobject-structure.md) , которые предоставляют сведения обо всех объектах. Коллекция может также включать [COR_HEAPOBJECT](cor-heapobject-structure.md) экземпляры, предоставляющие сведения об объектах, которые не находятся в корне ни в одном объекте, но еще не были собраны сборщиком мусора.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
