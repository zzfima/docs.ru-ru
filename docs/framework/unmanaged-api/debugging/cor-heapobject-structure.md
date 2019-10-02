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
ms.openlocfilehash: c59ddec655f3127e8dab8d8c41543f03a896cf63
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274037"
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`address`|Адрес объекта в памяти.|  
|`size`|Общий размер объекта в байтах.|  
|`type`|Токен [COR_TYPEID](cor-typeid-structure.md) , представляющий тип объекта.|  
  
## <a name="remarks"></a>Примечания  
 `COR_HEAPOBJECT`экземпляры можно получить, перечисляя объект интерфейса [икордебугхеапенум](icordebugheapenum-interface.md) , который заполняется путем вызова метода [метод ICorDebugProcess5:: енумератехеап](icordebugprocess5-enumerateheap-method.md) .  
  
 `COR_HEAPOBJECT` Экземпляр предоставляет сведения об активном объекте в управляемой куче или об объекте, который не является корневым для какого-либо объекта, но еще не был собран сборщиком мусора.  
  
 Для повышения производительности `COR_HEAPOBJECT.address` поле `CORDB_ADDRESS` является значением, а не значением интерфейса ICorDebugValue, которое используется в большинстве API отладки. Чтобы получить объект ICorDebugValue для заданного адреса объекта, можно передать `CORDB_ADDRESS` значение в метод [метод ICorDebugProcess5:: GetObject](icordebugprocess5-getobject-method.md) .  
  
 Для повышения производительности `COR_HEAPOBJECT.type` поле `COR_TYPEID` является значением, а не значением интерфейса ICorDebugType, которое используется в большинстве API отладки. Чтобы получить объект ICorDebugType для заданного идентификатора типа, можно передать `COR_TYPEID` значение в метод [метод ICorDebugProcess5:: жеттипефортипеид](icordebugprocess5-gettypefortypeid-method.md) .  
  
 Структура `COR_HEAPOBJECT` включает в себя COM-интерфейс, подсчитанный по ссылке. При извлечении `COR_HEAPOBJECT` экземпляра из перечислителя путем вызова метода [икордебугхеапенум:: Next](icordebugheapenum-next-method.md) необходимо впоследствии освободить ссылку.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
