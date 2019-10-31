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
ms.openlocfilehash: f37bf545553045b9737b7057feed78e1f06ace4d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099471"
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
  
|Член|Описание|  
|------------|-----------------|  
|`componentID`|Идентификатор типа объектов, содержащихся в массиве.|  
|`componentType`|Значение перечисления Корелементтипе, указывающее, является ли компонент ссылкой для сборки мусора, классом значения или примитивом.|  
|`firstElementOffset`|Смещение к первому элементу в массиве.|  
|`elementSize`|Размер каждого элемента.|  
|`countOffset`|Смещение к числу элементов в массиве.|  
|`rankSize`|Размер ранга в байтах.|  
|`numRanks`|Число рангов в массиве.|  
|`rankOffset`|Смещение, с которого начинается ранжирование.|  
  
## <a name="remarks"></a>Заметки  
 Поле `rankSize` задает размер ранжирования в многомерном массиве. Точны также для одномерных массивов.  
  
 Значение `numRanks` равно 1 для одномерного массива и `N` многомерного массива измерений `N`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
