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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220407"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="f6e6c-102">Функция CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="f6e6c-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="f6e6c-103">Освобождает ресурсы, выделенные для [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="f6e6c-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6e6c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6e6c-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6e6c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f6e6c-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="f6e6c-106">[в, из] Информация об отметке времени выпуска.</span><span class="sxs-lookup"><span data-stu-id="f6e6c-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="f6e6c-107">См. в разделе [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="f6e6c-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6e6c-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f6e6c-108">Return Value</span></span>  
 `S_OK` <span data-ttu-id="f6e6c-109">Если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="f6e6c-109">if the function succeeds.</span></span> <span data-ttu-id="f6e6c-110">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="f6e6c-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6e6c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f6e6c-111">See also</span></span>

- [<span data-ttu-id="f6e6c-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="f6e6c-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
