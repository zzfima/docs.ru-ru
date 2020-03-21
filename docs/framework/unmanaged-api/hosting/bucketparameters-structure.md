---
title: Структура BucketParameters
ms.date: 03/30/2017
api_name:
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
ms.openlocfilehash: 4d9de489bdeb0ab506f56ff08f4afb4cf6d0ab4f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178277"
---
# <a name="bucketparameters-structure"></a>Структура BucketParameters
Хранит имя типа события и параметры текущего исключения, связанного с событием.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;
    WCHAR pszEventTypeName[255];
    WCHAR pszParams[10][255];
} BucketParameters;  
```  
  
## <a name="members"></a>Члены  
  
|Участник|Описание|  
|------------|-----------------|  
|`fInited`|`true`, если остальная часть этой структуры действительна; в `false`противном случае, .|  
|`pszEventTypeName`|Название типа события.|  
|`pszParams`|Массив строк, каждая из которых определяет параметр для текущего исключения, связанного с событием.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
