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
ms.openlocfilehash: 270360a8950197eca14e02a60554659e5ac7b91c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099077"
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
  
|Член|Описание|  
|------------|-----------------|  
|`address`|Адрес объекта в памяти.|  
|`size`|Общий размер объекта в байтах.|  
|`type`|Токен [COR_TYPEID](cor-typeid-structure.md) , представляющий тип объекта.|  
  
## <a name="remarks"></a>Заметки  
 `COR_HEAPOBJECT` экземпляры можно получить, перечисляя объект интерфейса [икордебугхеапенум](icordebugheapenum-interface.md) , который заполняется путем вызова метода [метод ICorDebugProcess5:: енумератехеап](icordebugprocess5-enumerateheap-method.md) .  
  
 `COR_HEAPOBJECT` экземпляр предоставляет сведения об активном объекте в управляемой куче или об объекте, который не является корневым для какого-либо объекта, но еще не был собран сборщиком мусора.  
  
 Для повышения производительности `COR_HEAPOBJECT.address` поле — это `CORDB_ADDRESS` значение, а не значение интерфейса ICorDebugValue, используемое в большинстве API отладки. Чтобы получить объект ICorDebugValue для заданного адреса объекта, можно передать значение `CORDB_ADDRESS` в метод [метод ICorDebugProcess5:: GetObject](icordebugprocess5-getobject-method.md) .  
  
 Для повышения производительности `COR_HEAPOBJECT.type` поле — это `COR_TYPEID` значение, а не значение интерфейса ICorDebugType, используемое в большинстве API отладки. Чтобы получить объект ICorDebugType для заданного идентификатора типа, можно передать значение `COR_TYPEID` в метод [метод ICorDebugProcess5:: жеттипефортипеид](icordebugprocess5-gettypefortypeid-method.md) .  
  
 Структура `COR_HEAPOBJECT` включает в себя COM-интерфейс, подсчитанный по ссылке. При извлечении экземпляра `COR_HEAPOBJECT` из перечислителя путем вызова метода [икордебугхеапенум:: Next](icordebugheapenum-next-method.md) необходимо впоследствии освободить ссылку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
