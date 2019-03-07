---
title: Функция CertFreeAuthenticodeTimestamperInfo
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 082ed24eb65de12f337ab4a379b088da0f6eea5a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497383"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a>Функция CertFreeAuthenticodeTimestamperInfo
Освобождает ресурсы, выделенные для [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pTimestamperInfo`  
 [в, из] Информация об отметке времени выпуска. См. в разделе [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) структуры.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`, если функция выполняется успешно. В противном случае возвращается код ошибки.  
  
## <a name="see-also"></a>См. также
- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
