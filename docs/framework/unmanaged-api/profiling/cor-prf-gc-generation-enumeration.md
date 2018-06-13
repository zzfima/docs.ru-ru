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
ms.openlocfilehash: 8283139566050b1858a003316dc46581822a9bbb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450158"
---
# <a name="corprfgcgeneration-enumeration"></a>Перечисление COR_PRF_GC_GENERATION
Идентифицирует Создание сбора мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
 Сборщик мусора повышает производительность управления памятью посредством деления объектов в виде поколений на основе возраста. Сборщик мусора в настоящее время использует три поколения с номерами от 0, 1, 2, а также специальный сегмент куч, используемый для больших объектов. Объекты, размер которых превышает определенное значение, хранятся в куче больших объектов. Другие выделенные объекты запустите относятся к поколению 0. Все объекты, существующие после сборки мусора в поколении 0 продвигаются в поколение 1. Объекты, существующие после сборки мусора в поколении 1, переводятся в поколение 2.  
  
 Использование поколения означает, что сборщик мусора должен работать с подмножеством выделенные объекты в любой момент времени.  
  
 `COR_PRF_GC_GENERATION` Перечисление используется методом [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) структуры.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
