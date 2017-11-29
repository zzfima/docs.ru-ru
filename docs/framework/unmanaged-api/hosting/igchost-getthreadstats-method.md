---
title: "Метод IGCHost::GetThreadStats"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.GetThreadStats
api_location: mscoree.dll
api_type: COM
f1_keywords: GetThreadStats
helpviewer_keywords:
- IGCHost::GetThreadStats method [.NET Framework hosting]
- GetThreadStats method [.NET Framework hosting]
ms.assetid: 826baa9b-9218-4736-a509-7ab193b125a0
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7bfd6b89c3220e071a477e0c5b85e4ee57289762
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="igchostgetthreadstats-method"></a>Метод IGCHost::GetThreadStats
Получает статистику отдельного потока для сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pFiberCookie`  
 [in] Указатель Многослойный файл cookie, указывающее поток, для которого требуется извлечь статистику.  
  
 `pStats`  
 [in, out] Указатель на [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) структуру, содержащую статистику сборки мусора для заданного потока.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** GCHost.idl, GCHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Igchost-интерфейс](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
