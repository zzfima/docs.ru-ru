---
title: "Метод IGCHost::SetGCStartupLimits"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.SetGCStartupLimits
api_location: mscoree.dll
api_type: COM
f1_keywords: SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f95e5afa1297602e4ef12ed0dfb3f98aa5c762ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="igchostsetgcstartuplimits-method"></a>Метод IGCHost::SetGCStartupLimits
Задает размер сегмента и максимальный размер для поколения 0.  
  
> [!IMPORTANT]
>  Начиная с [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], можно задать размер сегмента и максимальное поколения 0 размер значения больше, чем `DWORD` с помощью [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `SegmentSize`  
 [in] Размер сегментов, используемых сборщик мусора.  
  
 `MaxGen0Size`  
 [in] Максимальный размер для поколения 0.  
  
## <a name="remarks"></a>Примечания  
 `SetGCStartupLimits` Метод может вызываться только один раз. Эти значения невозможно изменить позже.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** GCHost.idl, GCHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Igchost-интерфейс](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
