---
title: Структура CLR_DEBUGGING_VERSION
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87f938a7119abe4a88da65bd779a5f4a02499516
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996350"
---
# <a name="clrdebuggingversion-structure"></a>Структура CLR_DEBUGGING_VERSION
Определяет версию продукта среды CLR, предназначенную для отладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`wStructVersion`|Номер версии структуры.|  
|`wMajor`|Основной номер версии.|  
|`wMinor`|Дополнительный номер версии.|  
|`wBuild`|Номер сборки.|  
|`wRevision`|Номер редакции.|  
  
## <a name="remarks"></a>Примечания  
 `CLR_DEBUGGING_VERSION` Структура является таким же, как структура COR_VERSION, тем не менее, `CLR_DEBUGGING_VERSION` структура предоставляет дополнительное поле версии структуры (`wStructVersion`). В настоящее время это поле должен быть равным нулю.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
