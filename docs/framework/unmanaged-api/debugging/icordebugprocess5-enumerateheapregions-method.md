---
title: Метод ICorDebugProcess5::EnumerateHeapRegions
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeapRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type:
- apiref
ms.openlocfilehash: 8070b0693b5718ad8b4cbeb9bf5792cb7f4a0a85
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792403"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a>Метод ICorDebugProcess5::EnumerateHeapRegions
Возвращает перечислитель для диапазонов памяти управляемой кучи.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppRegions`  
 заполняет Указатель на адрес объекта интерфейса [икордебугхеапсегментенум](icordebugheapsegmentenum-interface.md) , который является перечислителем для диапазонов памяти, в которых объекты находятся в управляемой куче.  
  
## <a name="remarks"></a>Заметки  
 Перед вызовом метода `ICorDebugProcess5::EnumerateHeapRegions` необходимо вызвать метод [метод ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) и проверить значение поля `areGCStructuresValid` возвращаемого [COR_HEAPINFO](cor-heapinfo-structure.md) объекта, чтобы гарантировать, что куча сборки мусора в ее текущем состоянии является перечислимым. Кроме того, метод `ICorDebugProcess5::EnumerateHeapRegions` возвращает `E_FAIL`, если во время существования процесса присоединяется слишком рано, до создания областей памяти.  
  
 Этот метод гарантирует перечисление всех областей памяти, которые могут содержать управляемые объекты, но не гарантирует, что управляемые объекты фактически находятся в этих регионах. Объект коллекции [икордебугхеапсегментенум](icordebugheapsegmentenum-interface.md) может включать в себя пустые или зарезервированные регионы памяти.  
  
 Объект интерфейса [икордебугхеапсегментенум](icordebugheapsegmentenum-interface.md) является стандартным перечислителем, производным от интерфейса ICorDebugEnum, который позволяет перечислить [COR_SEGMENTные](cor-segment-structure.md) объекты. Каждый объект [COR_SEGMENT](cor-segment-structure.md) предоставляет сведения о диапазоне памяти определенного сегмента вместе с поколением объектов в этом сегменте.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
