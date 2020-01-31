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
ms.openlocfilehash: 4eff8472e353c4e5fd2505b281cc9efc89f013fc
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867221"
---
# <a name="cor_prf_gc_generation-enumeration"></a>Перечисление COR_PRF_GC_GENERATION
Определяет создание коллекции мусора.  
  
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
|`COR_PRF_GC_GEN_0`|Объект сохраняется как поколение 0.|  
|`COR_PRF_GC_GEN_1`|Объект сохраняется как поколение 1.|  
|`COR_PRF_GC_GEN_2`|Объект сохраняется как поколение 2.|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|Объект хранится в куче больших объектов.|  
  
## <a name="remarks"></a>Заметки  
 Сборщик мусора повышает производительность управления памятью, разделив объекты на поколения на основе возраста. Сборщик мусора в настоящее время использует три поколения, нумерованный 0, 1 и 2, а также специальный сегмент кучи, используемый для больших объектов. Объекты, размер которых больше определенного значения, хранятся в куче больших объектов. Другие выделенные объекты начинают принадлежать к поколению 0. Все объекты, существующие после сборки мусора в поколении 0, переходят в поколение 1. Объекты, существующие после сборки мусора в поколении 1, переходят в поколение 2.  
  
 Использование поколений означает, что сборщик мусора должен работать только с подмножеством выделенных объектов в один момент времени.  
  
 Перечисление `COR_PRF_GC_GENERATION` используется структурой [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления профилирования](profiling-enumerations.md)
