---
title: Перечисление COR_PRF_STATIC_TYPE
ms.date: 03/30/2017
api_name:
- COR_PRF_STATIC_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_STATIC_TYPE
helpviewer_keywords:
- COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type:
- apiref
ms.openlocfilehash: 40efe81f72a2043503bf521e3e47dad1a7f4530c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448451"
---
# <a name="cor_prf_static_type-enumeration"></a>Перечисление COR_PRF_STATIC_TYPE
Указывает, является ли поле статическим и, если да, относящееся к этому полю статическое качество. Эти значения можно комбинировать с помощью побитовой операции OR, чтобы указать, что поле имеет несколько различных статических качеств.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|Поле не является статическим.|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|Поле является статическим в домене приложения.|  
|`COR_PRF_FIELD_THREAD_STATIC`|Поле является статическим для потока.|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|Поле является статическим по контексту.|  
|`COR_PRF_FIELD_RVA_STATIC`|Поле является относительным виртуальным адресом (RVA) — статическим.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
