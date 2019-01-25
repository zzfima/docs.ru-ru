---
title: Метод IGCHost::GetStats
ms.date: 03/30/2017
api_name:
- IGCHost.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d9a3775f453cb432ce6b92d067f93ca54c329c06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674184"
---
# <a name="igchostgetstats-method"></a>Метод IGCHost::GetStats
Получает статистику для текущего состояния сборщик мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pStats`  
 [in, out] Указатель на [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) структуру, которая содержит статистические данные для текущего состояния сборщик мусора.  
  
## <a name="remarks"></a>Примечания  
 Статистику можно с помощью системы оптимального распределения помогут сборщик мусора работают. Например, система распределения может определить, просмотрев статистические данные, необходимо установить дополнительную память или принудительно коллекции.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** GCHost.idl GCHost.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IGCHost](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
