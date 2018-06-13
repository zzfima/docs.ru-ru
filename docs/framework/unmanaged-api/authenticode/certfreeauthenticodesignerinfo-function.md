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
ms.openlocfilehash: 84f15dc49d14e781f69d0f9da8f314eb71d8c034
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401620"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="88474-102">Функция CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="88474-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="88474-103">Освобождает ресурсы, выделенные для [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="88474-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88474-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88474-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="88474-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="88474-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="88474-106">[в, из] Информация о подписавшем, которую необходимо указывать.</span><span class="sxs-lookup"><span data-stu-id="88474-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="88474-107">В разделе [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="88474-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88474-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="88474-108">Return Value</span></span>  
 <span data-ttu-id="88474-109">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="88474-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="88474-110">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="88474-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88474-111">См. также</span><span class="sxs-lookup"><span data-stu-id="88474-111">See Also</span></span>  
 [<span data-ttu-id="88474-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="88474-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
