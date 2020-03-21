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
ms.openlocfilehash: f5af8e559b4fbfeb60530372185ca10104ade987
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178849"
---
# <a name="icordebugheapenumnext-method"></a>Метод ICorDebugHeapEnum::Next
Получает указанное количество [COR_HEAPOBJECT](cor-heapobject-structure.md) экземпляров, содержащих информацию об объектах на управляемой куче.  
  
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
  
 объекты  
 (ваут) Массив указателей, каждый из которых указывает на [COR_HEAPOBJECT](cor-heapobject-structure.md) объект, предоставляющий информацию об объекте на управляемой куче.  
  
 pceltFetched  
 (ваут) Указатель на количество [COR_HEAPOBJECT](cor-heapobject-structure.md) объектов `objects`фактически вернулся в . Это значение может быть `null`, если параметр `celt` имеет значение 1.  
  
## <a name="remarks"></a>Remarks  
 Поле `COR_HEAPOBJECT.type` является идентификатором вложенного COM-интерфейса с подсчетом ссылок. Эта ссылка должна быть выпущена вызывающим объектом `ICorDebugHeapEnum::Next`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugHeapEnum](icordebugheapenum-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
