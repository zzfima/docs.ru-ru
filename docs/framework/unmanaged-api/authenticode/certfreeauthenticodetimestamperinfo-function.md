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
ms.openlocfilehash: 680d9c959c57620ff38f8e785c670b451e5805b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741234"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="e73b7-102">Функция CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="e73b7-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="e73b7-103">Освобождает ресурсы, выделенные для [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="e73b7-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e73b7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e73b7-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e73b7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e73b7-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="e73b7-106">[в, из] Информация об отметке времени выпуска.</span><span class="sxs-lookup"><span data-stu-id="e73b7-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="e73b7-107">См. в разделе [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="e73b7-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e73b7-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e73b7-108">Return Value</span></span>  
 <span data-ttu-id="e73b7-109">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="e73b7-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="e73b7-110">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="e73b7-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e73b7-111">См. также</span><span class="sxs-lookup"><span data-stu-id="e73b7-111">See also</span></span>

- [<span data-ttu-id="e73b7-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="e73b7-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
