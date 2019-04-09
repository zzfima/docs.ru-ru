---
title: Структура COR_HEAPOBJECT
ms.date: 03/30/2017
api_name:
- COR_HEAPOBJECT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPOBJECT
helpviewer_keywords:
- COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f179b58ff8eb51e2843780d3212cf38ed7d13216
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168835"
---
# <a name="corheapobject-structure"></a>Структура COR_HEAPOBJECT
Предоставляет сведения об объекте, находящемся в управляемой куче.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`address`|Адрес объекта в памяти.|  
|`size`|Общий размер объекта, в байтах.|  
|`type`|Объект [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) токен, представляющий тип объекта.|  
  
## <a name="remarks"></a>Примечания  
 `COR_HEAPOBJECT` экземпляры можно получить посредством перечисления [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) объект интерфейса, который заполняется путем вызова [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) метод.  
  
 Объект `COR_HEAPOBJECT` экземпляр предоставляет сведения о активный объект в управляемой куче, либо об объекте, который не является корневым, любой объект, но еще не были собраны сборщик мусора.  
  
 Для повышения производительности `COR_HEAPOBJECT.address` поле является `CORDB_ADDRESS` значение вместо ICorDebugValue интерфейс значение, используемое во многом API отладки. Чтобы получить объект ICorDebugValue для адреса заданного объекта, можно передать `CORDB_ADDRESS` значение [ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) метод.  
  
 Для повышения производительности `COR_HEAPOBJECT.type` поле является `COR_TYPEID` значение вместо ICorDebugType интерфейс значение, используемое во многом API отладки. Чтобы получить объект ICorDebugType идентификатора заданного типа, можно передать `COR_TYPEID` значение [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) метод.  
  
 `COR_HEAPOBJECT` Структура включает в себя COM-интерфейса с подсчетом ссылок. Если вы получите `COR_HEAPOBJECT` экземпляр из перечислителя, вызвав [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) метод, впоследствии необходимо освободить ссылку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
