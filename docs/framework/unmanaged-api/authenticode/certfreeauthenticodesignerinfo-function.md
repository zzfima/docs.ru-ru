---
title: Функция CertFreeAuthenticodeSignerInfo
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbed2ece8b10c6385341c0af44a81dfa16b6f60c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497487"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="7abd4-102">Функция CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="7abd4-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="7abd4-103">Освобождает ресурсы, выделенные для [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="7abd4-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7abd4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7abd4-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7abd4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7abd4-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="7abd4-106">[в, из] Информация о подписавшем, которую необходимо указывать.</span><span class="sxs-lookup"><span data-stu-id="7abd4-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="7abd4-107">См. в разделе [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="7abd4-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7abd4-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7abd4-108">Return Value</span></span>  
 <span data-ttu-id="7abd4-109">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="7abd4-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="7abd4-110">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="7abd4-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7abd4-111">См. также</span><span class="sxs-lookup"><span data-stu-id="7abd4-111">See also</span></span>
- [<span data-ttu-id="7abd4-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="7abd4-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
