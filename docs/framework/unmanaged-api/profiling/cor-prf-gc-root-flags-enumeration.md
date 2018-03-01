---
title: "Перечисление COR_PRF_GC_ROOT_FLAGS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- COR_PRF_GC_ROOT_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords:
- COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5e00f695edb94acbd54d6bd009ccd629aeec1b14
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corprfgcrootflags-enumeration"></a>Перечисление COR_PRF_GC_ROOT_FLAGS
Указывает свойства корня сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|Корень предотвращает мусора переместить объект.|  
|`COR_PRF_GC_ROOT_WEAKREF`|Корень не предотвращает сбора мусора.|  
|`COR_PRF_GC_ROOT_INTERIOR`|Корень ссылается на поле объекта, а не сам объект.|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|Корневой предотвращает сбора мусора, если количество ссылок на объект определенного значения.|  
  
## <a name="remarks"></a>Примечания  
 `COR_PRF_GC_ROOT_FLAGS`представляет собой битовую маску, предоставляющий дополнительные сведения об особых корнях. Однако не все корни являются особыми. Например некоторые корни не слабые ссылки внутренних указателей, закрепленных или подсчетом ссылок. Для таких корней отсутствуют флаги для передачи. Таким образом, методы, использующие это перечисление, такие как [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) метода send 0 для битовой маски флагов, указывающее, что все флаги выключены.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
