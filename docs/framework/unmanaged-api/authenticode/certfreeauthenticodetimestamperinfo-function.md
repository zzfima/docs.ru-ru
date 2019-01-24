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
ms.openlocfilehash: 27c16cb5d85ddffc1646bee893c5644682812025
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560585"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a>Функция CertFreeAuthenticodeTimestamperInfo
Освобождает ресурсы, выделенные для [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pTimestamperInfo`  
 [в, из] Информация об отметке времени выпуска. См. в разделе [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) структуры.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`, если функция выполняется успешно. В противном случае возвращается код ошибки.  
  
## <a name="see-also"></a>См. также
- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
