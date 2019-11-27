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
ms.openlocfilehash: 2b01acbd617b13a64ef3dca6c8661f1e6bb067ac
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447379"
---
# <a name="cor_prf_function_argument_info-structure"></a>Структура COR_PRF_FUNCTION_ARGUMENT_INFO
Представляет аргументы функции слева направо.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`numRanges`|Число блоков аргументов. То есть это значение равно количеству структур [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) в массиве `ranges`.|  
|`totalArgumentSize`|Общий размер всех аргументов. Иными словами, это значение является суммой длин аргументов.|  
|`ranges`|Массив структур `COR_PRF_FUNCTION_ARGUMENT_RANGE`, каждый из которых представляет один блок аргументов функции.|  
  
## <a name="remarks"></a>Примечания  
 У функции может быть несколько аргументов. Эти аргументы могут не храниться непрерывно в памяти. У вас может быть блок из трех аргументов в одном месте, блок из двух аргументов в другом месте и последний блок одного аргумента в другом месте. Все эти аргументы используются для одной и той же функции. они просто хранятся в разных местах.  
  
 Структура `COR_PRF_FUNCTION_ARGUMENT_INFO` представляет все аргументы одной функции. Он использует массив для ссылки на все блоки аргументов функции. Таким образом, для одной функции имеется одна структура `COR_PRF_FUNCTION_ARGUMENT_INFO`, которая ссылается на несколько `COR_PRF_FUNCTION_ARGUMENT_RANGE`ных структур, каждая из которых указывает на один или несколько аргументов функции.  
  
 Аргументы, хранимые в регистрах, загружаются в память для построения структур.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Структуры профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
