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
ms.openlocfilehash: 9c37a9af6a1532d03fa04ca151605cef7ab5244e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401772"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="0b1f8-102">Функция CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="0b1f8-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="0b1f8-103">Освобождает ресурсы, выделенные для [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="0b1f8-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b1f8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b1f8-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0b1f8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0b1f8-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="0b1f8-106">[в, из] Информация об отметке времени выпуска.</span><span class="sxs-lookup"><span data-stu-id="0b1f8-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="0b1f8-107">В разделе [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="0b1f8-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b1f8-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0b1f8-108">Return Value</span></span>  
 <span data-ttu-id="0b1f8-109">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="0b1f8-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="0b1f8-110">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="0b1f8-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b1f8-111">См. также</span><span class="sxs-lookup"><span data-stu-id="0b1f8-111">See Also</span></span>  
 [<span data-ttu-id="0b1f8-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="0b1f8-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
