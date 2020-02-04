---
title: Метод ICorDebugHeapEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type:
- apiref
ms.openlocfilehash: 2c84112984e9cb7dec2a492ac16af00e14770806
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782483"
---
# <a name="icordebugheapenumnext-method"></a>Метод ICorDebugHeapEnum::Next
Возвращает указанное число экземпляров [COR_HEAPOBJECT](cor-heapobject-structure.md) , содержащих сведения об объектах в управляемой куче.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Параметры  
 celt  
 [in] Количество объектов, которые должны быть получены.  
  
 Azure  
 заполняет Массив указателей, каждый из которых указывает на объект [COR_HEAPOBJECT](cor-heapobject-structure.md) , предоставляющий сведения об объекте в управляемой куче.  
  
 pceltFetched  
 заполняет Указатель на число объектов [COR_HEAPOBJECT](cor-heapobject-structure.md) , фактически возвращаемых в `objects`. Это значение может быть `null`, если параметр `celt` имеет значение 1.  
  
## <a name="remarks"></a>Заметки  
 Поле `COR_HEAPOBJECT.type` является идентификатором вложенного COM-интерфейса с подсчетом ссылок. Эта ссылка должна быть выпущена вызывающим объектом `ICorDebugHeapEnum::Next`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugHeapEnum](icordebugheapenum-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
