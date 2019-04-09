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
ms.openlocfilehash: bdb764417b757cd7388c49d7e5cac9a960074820
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142406"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="6d43b-102">Функция CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="6d43b-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="6d43b-103">Освобождает ресурсы, выделенные для [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="6d43b-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d43b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d43b-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d43b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6d43b-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="6d43b-106">[в, из] Информация о подписавшем, которую необходимо указывать.</span><span class="sxs-lookup"><span data-stu-id="6d43b-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="6d43b-107">См. в разделе [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="6d43b-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d43b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6d43b-108">Return Value</span></span>  
 `S_OK` <span data-ttu-id="6d43b-109">Если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="6d43b-109">if the function succeeds.</span></span> <span data-ttu-id="6d43b-110">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="6d43b-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d43b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="6d43b-111">See also</span></span>

- [<span data-ttu-id="6d43b-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="6d43b-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
