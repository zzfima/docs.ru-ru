---
title: Структура COR_PRF_FUNCTION_ARGUMENT_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 293ad30ebf47ca8684d158b1ae1772ab245d7981
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163121"
---
# <a name="corprffunctionargumentinfo-structure"></a>Структура COR_PRF_FUNCTION_ARGUMENT_INFO
Представляет аргументы функции слева направо.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`numRanges`|Число блоков аргументов. Это значение является число [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) структур в `ranges` массива.|  
|`totalArgumentSize`|Общий размер всех аргументов. Другими словами это значение является суммой длин аргументов.|  
|`ranges`|Массив `COR_PRF_FUNCTION_ARGUMENT_RANGE` структуры, каждый из которых представляет один блок аргументов функции.|  
  
## <a name="remarks"></a>Примечания  
 Функция может иметь много аргументов. Эти аргументы могут храниться в памяти не непрерывно. Возможно, блок из трех аргументов в одном месте, блок из двух аргументов в другом месте и конечный блок одного аргумента в другом месте. Эти аргументы являются все для той же функции; они просто хранятся в разных местах.  
  
 `COR_PRF_FUNCTION_ARGUMENT_INFO` Структура представляет все аргументы одной функции. Она использует массив для ссылки на все блоки аргументов функции. Таким образом, для одной функции, у вас есть один `COR_PRF_FUNCTION_ARGUMENT_INFO` структуру, которая ссылается на несколько `COR_PRF_FUNCTION_ARGUMENT_RANGE` структуры, каждый из которых указывает на один или несколько аргументов функции.  
  
 Аргументы, которые хранятся в регистрах, распределяются в памяти для построения структур.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
