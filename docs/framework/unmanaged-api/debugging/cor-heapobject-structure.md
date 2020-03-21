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
ms.openlocfilehash: efb3d913e1d8ef0c486d7e5e1d9777ae7d88bc71
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179340"
---
# <a name="cor_heapobject-structure"></a>Структура COR_HEAPOBJECT
Предоставляет сведения об объекте, находящемся в управляемой куче.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;
    ULONG64 size;
    COR_TYPEID type;
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a>Члены  
  
|Участник|Описание|  
|------------|-----------------|  
|`address`|Адрес объекта в памяти.|  
|`size`|Общий размер объекта, в байтах.|  
|`type`|[Знак COR_TYPEID,](cor-typeid-structure.md) представляющий тип объекта.|  
  
## <a name="remarks"></a>Remarks  
 `COR_HEAPOBJECT`экземпляры можно извлечь, перечислив объект интерфейса [ICorDebugHeapEnum,](icordebugheapenum-interface.md) который населен, позвонив в метод [ICorDebugProcess5::EnumerateHeap.](icordebugprocess5-enumerateheap-method.md)  
  
 Экземпляр `COR_HEAPOBJECT` предоставляет информацию либо о живом объекте на управляемой куче, либо об объекте, который не коренится ни одним объектом, но еще не собран сборщиком мусора.  
  
 Для повышения производительности `COR_HEAPOBJECT.address` поле `CORDB_ADDRESS` представляет собой значение, а не значение интерфейса ICorBugValue, используемого в большей части API отладки. Чтобы получить объект ICorDebugValue для данного адреса `CORDB_ADDRESS` объекта, можно передать значение методу [ICorDebugProcess5::GetObject.](icordebugprocess5-getobject-method.md)  
  
 Для повышения производительности `COR_HEAPOBJECT.type` поле `COR_TYPEID` является ценностью, а не значением интерфейса ICorDebugType, используемого в большей части API отладки. Чтобы получить объект ICorDebugType для идентификатора заданного типа, вы можете передать `COR_TYPEID` значение методу [ICorDebugProcess5:GetTypeForTypeID.](icordebugprocess5-gettypefortypeid-method.md)  
  
 Структура `COR_HEAPOBJECT` включает в себя справочно-считаемый интерфейс COM. Если вы извлекете `COR_HEAPOBJECT` экземпляр из регистратора, позвонив в [ICorDebugHeapEnum::Следующий](icordebugheapenum-next-method.md) метод, вы должны впоследствии освободить ссылку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры отладки](debugging-structures.md)
- [Отладки](index.md)
