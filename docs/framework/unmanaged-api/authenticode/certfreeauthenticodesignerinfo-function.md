---
title: "Функция CertFreeAuthenticodeSignerInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CertFreeAuthenticodeSignerInfo
api_location: clr.dll
api_type: DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8b38d30a1323d0d44330b8bb9a006c372ea7780
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="09028-102">Функция CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="09028-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="09028-103">Освобождает ресурсы, выделенные для [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="09028-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09028-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09028-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="09028-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="09028-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="09028-106">[в, из] Информация о подписавшем, которую необходимо указывать.</span><span class="sxs-lookup"><span data-stu-id="09028-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="09028-107">В разделе [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="09028-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09028-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="09028-108">Return Value</span></span>  
 <span data-ttu-id="09028-109">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="09028-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="09028-110">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="09028-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09028-111">См. также</span><span class="sxs-lookup"><span data-stu-id="09028-111">See Also</span></span>  
 [<span data-ttu-id="09028-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="09028-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
