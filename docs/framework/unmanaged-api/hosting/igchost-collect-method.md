---
title: Метод IGCHost::Collect
ms.date: 03/30/2017
api_name:
- IGCHost.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bce005a677dcb74c176a6dddfb2726f6b1fd0e8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436911"
---
# <a name="igchostcollect-method"></a>Метод IGCHost::Collect
Принудительно вызывает сборку мусора для данного поколения, независимо от состояния текущей сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `Generation`  
 [in] Поколение, для которого требуется выполнить сборку мусора. Значение -1 указывает, что все поколения пройдут сборку мусора.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** GCHost.idl, GCHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IGCHost](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
