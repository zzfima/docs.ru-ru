---
title: Перечисление ESymbolReadingPolicy
ms.date: 03/30/2017
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ba29952fe4a6edfc6e9e80ec02f82de65ef0064
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208427"
---
# <a name="esymbolreadingpolicy-enumeration"></a>Перечисление ESymbolReadingPolicy
Содержит значения, задавать политику для чтения файлов базы данных (PDB).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`eSymbolReadingAlways`|Указывает, что отладчик должен всегда считывать PDB-файлы.|  
|`eSymbolReadingFullTrustOnly`|Указывает, что отладчик должен считывать только PDB-файлы, которые связаны с полным доверием.|  
|`eSymbolReadingNever`|Указывает, что отладчик не должен считывать PDB-файлы.|  
  
## <a name="remarks"></a>Примечания  
 `ESymbolReadingPolicy` Перечисление используется с [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
