---
title: Перечисление COR_PRF_GC_GENERATION
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION
helpviewer_keywords:
- COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 74e70f58600205d44a9ba052981b2cc67b3a44ec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753808"
---
# <a name="corprfgcgeneration-enumeration"></a>Перечисление COR_PRF_GC_GENERATION
Идентифицирует поколение сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|Объект хранится в виде поколения 0.|  
|`COR_PRF_GC_GEN_1`|Объект хранится в виде поколения 1.|  
|`COR_PRF_GC_GEN_2`|Объект хранится в виде поколения 2.|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|Объект хранится в куче больших объектов.|  
  
## <a name="remarks"></a>Примечания  
 Сборщик мусора повышает производительность управления памятью посредством деления объектов в виде поколений, на основе возраста. Сборщик мусора в настоящее время использует три поколения с номерами от 0, 1 и 2, а также специальной куче сегмент, который используется для больших объектов. Объекты, размер которых превышает определенное значение, хранятся в куче больших объектов. Другие выделенные объекты начинают относятся к поколению 0. Все объекты, существующие после сборки мусора в поколении 0, продвигаются в поколение 1. Объекты, существующие после сборки мусора в поколении 1, переводятся в поколение 2.  
  
 Использование поколения означает, что сборщик мусора приходится работать с набором выделенных объектов в любой момент времени.  
  
 `COR_PRF_GC_GENERATION` Перечисление, используемое [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) структуры.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
