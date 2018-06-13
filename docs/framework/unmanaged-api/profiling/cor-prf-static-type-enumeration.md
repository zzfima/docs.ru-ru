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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fc610f4cc34b256867396a3390d5ccd0822f6454
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450392"
---
# <a name="corprfstatictype-enumeration"></a>Перечисление COR_PRF_STATIC_TYPE
Указывает, является ли поле статическим и, если да, относящееся к этому полю статическое качество. Эти значения могут быть объединены с помощью побитовой операции или для указания, что поле имеет несколько различных статических качеств.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|Поле не является статическим.|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|Поле является статическим в домене приложения.|  
|`COR_PRF_FIELD_THREAD_STATIC`|Поля статического потока.|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|Это поле является статическим в контексте.|  
|`COR_PRF_FIELD_RVA_STATIC`|Поле является относительный виртуальный адрес (RVA)-статический.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
