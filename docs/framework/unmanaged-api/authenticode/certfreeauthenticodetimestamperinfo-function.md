---
title: "Функция CertFreeAuthenticodeTimestamperInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CertFreeAuthenticodeTimestamperInfo
api_location: clr.dll
api_type: DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 353bba880cfa8a5ecf9ed826fbb529e31f790a12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="b1ec6-102">Функция CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="b1ec6-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="b1ec6-103">Освобождает ресурсы, выделенные для [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="b1ec6-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1ec6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1ec6-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1ec6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b1ec6-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="b1ec6-106">[в, из] Информация об отметке времени выпуска.</span><span class="sxs-lookup"><span data-stu-id="b1ec6-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="b1ec6-107">В разделе [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="b1ec6-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1ec6-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b1ec6-108">Return Value</span></span>  
 <span data-ttu-id="b1ec6-109">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="b1ec6-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="b1ec6-110">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="b1ec6-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1ec6-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b1ec6-111">See Also</span></span>  
 [<span data-ttu-id="b1ec6-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="b1ec6-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
