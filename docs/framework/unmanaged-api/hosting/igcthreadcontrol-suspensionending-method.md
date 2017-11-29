---
title: "Метод IGCThreadControl::SuspensionEnding"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCThreadControl.SuspensionEnding
api_location: mscoree.dll
api_type: COM
f1_keywords: SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e4460d2b0eaf10d20ddd0c3641279a8ffc05c245
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="igcthreadcontrolsuspensionending-method"></a>Метод IGCThreadControl::SuspensionEnding
Уведомляет узел, что среда выполнения возобновляет выполнение после сборки мусора или по другой причине.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `Generation`  
 [in] Поколение, для которого был выполнен сбор мусора.  
  
## <a name="remarks"></a>Примечания  
 Не следует перепланировать каких-либо потоков во время `SuspensionEnding` обратного вызова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Igcthreadcontrol-интерфейс](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
