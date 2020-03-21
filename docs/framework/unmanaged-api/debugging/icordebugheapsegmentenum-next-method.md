---
title: Метод ICorDebugHeapSegmentEnum::Next
ms.date: 03/30/2017
api_name:
- Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type:
- apiref
ms.openlocfilehash: 8a267ec7123edb73ad51f0781a78344119ec6f21
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178898"
---
# <a name="icordebugheapsegmentenumnext-method"></a>Метод ICorDebugHeapSegmentEnum::Next
Получает указанное количество [COR_HEAPOBJECT](cor-heapobject-structure.md) экземпляров, содержащих информацию о регионах памяти управляемой кучи.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Параметры  
 celt  
 (в) Количество сегментов, которые необходимо получить.  
  
 сегменты  
 (ваут) Массив указателей, каждый из которых указывает на [COR_HEAPOBJECT](cor-heapobject-structure.md) объект, предоставляющий информацию о области памяти в управляемой куче.  
  
 pceltFetched  
 (ваут) Указатель на количество [COR_HEAPOBJECT](cor-heapobject-structure.md) объектов `segments`фактически вернулся в . Это значение может быть `null`, если параметр `celt` имеет значение 1.  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
