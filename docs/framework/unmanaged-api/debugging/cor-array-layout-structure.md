---
title: Структура COR_ARRAY_LAYOUT
ms.date: 03/30/2017
api_name:
- COR_ARRAY_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ARRAY_LAYOUT
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: aa20ac3d-6f60-4aa2-91c5-f3a86f82eba8
topic_type:
- apiref
ms.openlocfilehash: ca2d00611a7530dfb0d1c2a27123947bdf69820d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179342"
---
# <a name="cor_array_layout-structure"></a>Структура COR_ARRAY_LAYOUT
Предоставляет сведения о расположении объекта массива в памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct COR_ARRAY_LAYOUT {  
    COR_TYPEID componentID;  
    CorElementType componentType;  
    ULONG32 firstElementOffset;  
    ULONG32 elementSize;  
    ULONG32 countOffset;
    ULONG32 rankSize;
    ULONG32 numRanks;
    ULONG32 rankOffset;
} COR_ARRAY_LAYOUT;  
```  
  
## <a name="members"></a>Члены  
  
|Участник|Описание|  
|------------|-----------------|  
|`componentID`|Идентификатор типа объектов, содержащих массив.|  
|`componentType`|Значение перечисления CorElementType, которое указывает, является ли компонент ссылкой на сбор мусора, классом значений или примитивным.|  
|`firstElementOffset`|Смещение до первого элемента в массиве.|  
|`elementSize`|Размер каждого элемента.|  
|`countOffset`|Смещение с числом элементов в массиве.|  
|`rankSize`|Размер ранга, в байтах.|  
|`numRanks`|Количество званий в массиве.|  
|`rankOffset`|Смещение, с которого начинаются ряды.|  
  
## <a name="remarks"></a>Remarks  
 Поле `rankSize` определяет размер ранга в многомерном массиве. Это точно для одномерных массивов, а также.  
  
 Значение `numRanks` 1 для одномерного массива `N` и для многомерного массива измерений. `N`  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры отладки](debugging-structures.md)
- [Отладки](index.md)
