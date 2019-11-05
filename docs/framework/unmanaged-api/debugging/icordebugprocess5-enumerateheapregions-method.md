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
ms.openlocfilehash: 3ab4da3fcf43731587dae6f3a8e82ea48c5ee1ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129644"
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
 заполняет Указатель на адрес объекта интерфейса [икордебугхеапсегментенум](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) , который является перечислителем для диапазонов памяти, в которых объекты находятся в управляемой куче.  
  
## <a name="remarks"></a>Заметки  
 Перед вызовом метода `ICorDebugProcess5::EnumerateHeapRegions` необходимо вызвать метод [метод ICorDebugProcess5:: GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) и проверить значение поля `areGCStructuresValid` возвращенного объекта [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) , чтобы убедиться, что куча сборки мусора в ее Текущее состояние является перечислимым. Кроме того, метод `ICorDebugProcess5::EnumerateHeapRegions` возвращает `E_FAIL`, если во время существования процесса присоединяется слишком рано, до создания областей памяти.  
  
 Этот метод гарантирует перечисление всех областей памяти, которые могут содержать управляемые объекты, но не гарантирует, что управляемые объекты фактически находятся в этих регионах. Объект коллекции [икордебугхеапсегментенум](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) может включать в себя пустые или зарезервированные регионы памяти.  
  
 Объект интерфейса [икордебугхеапсегментенум](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) является стандартным перечислителем, производным от интерфейса ICorDebugEnum, который позволяет перечислять объекты [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) . Каждый объект [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) предоставляет сведения о диапазоне памяти определенного сегмента вместе с поколением объектов в этом сегменте.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
