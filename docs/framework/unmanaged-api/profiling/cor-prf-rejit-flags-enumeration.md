---
title: Перечисление COR_PRF_REJIT_FLAGS
ms.date: 08/06/2019
api_name:
- COR_PRF_REJIT_FLAGS Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_REJIT_FLAGS
helpviewer_keywords:
- COR_PRF_REJIT_FLAGS enumeration [.NET Framework profiling]
topic_type:
- apiref
author: davmason
ms.author: davmason
ms.openlocfilehash: 8fc5f1a488826d8adc6aecb8ef122609bebbe813
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177100"
---
# <a name="cor_prf_rejit_flags-enumeration"></a>Перечисление COR_PRF_REJIT_FLAGS
Содержит значения, указывающие на то, как должен вести себя [API ICorProfilerInfo10::RequestReJITInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum  
{
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a>Члены  
  
|Участник|Описание|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| Методы ReJITted будут заблокированы от встроенного в другие методы. |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| Получайте `GetFunctionParameters` обратные вызовы для любых методов, которые встраиваем в строку запрошенные методы, которые должны быть reJITted. |  

## <a name="requirements"></a>Требования  
 **Платформы:** Смотрите [операционные системы, поддерживаемые .NET Core.](../../../core/install/dependencies.md?pivots=os-windows)  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]
  
## <a name="see-also"></a>См. также раздел

- [Перечисления профилирования](profiling-enumerations.md)
