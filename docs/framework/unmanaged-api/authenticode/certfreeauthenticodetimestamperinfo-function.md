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
ms.openlocfilehash: 355e6c7b1cd77936d5ccfa5ccff7312c8e35ac63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941652"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="befc0-102">Функция CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="befc0-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="befc0-103">Освобождает ресурсы, выделенные для [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="befc0-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="befc0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="befc0-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="befc0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="befc0-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="befc0-106">[в, из] Информация об отметке времени выпуска.</span><span class="sxs-lookup"><span data-stu-id="befc0-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="befc0-107">См. в разделе [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="befc0-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="befc0-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="befc0-108">Return Value</span></span>  
 <span data-ttu-id="befc0-109">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="befc0-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="befc0-110">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="befc0-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="befc0-111">См. также</span><span class="sxs-lookup"><span data-stu-id="befc0-111">See also</span></span>

- [<span data-ttu-id="befc0-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="befc0-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
