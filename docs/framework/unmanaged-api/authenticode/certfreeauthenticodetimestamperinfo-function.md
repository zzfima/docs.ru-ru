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
ms.openlocfilehash: a8ecada29528b065ddad0abc80a850ee0f347f6b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787002"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="839d6-102">Функция CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="839d6-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="839d6-103">Освобождает ресурсы, выделенные для структуры [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="839d6-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="839d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="839d6-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="839d6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="839d6-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="839d6-106">[в, из] Информация об отметке времени выпуска.</span><span class="sxs-lookup"><span data-stu-id="839d6-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="839d6-107">См. структуру [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="839d6-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="839d6-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="839d6-108">Return Value</span></span>  
 <span data-ttu-id="839d6-109">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="839d6-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="839d6-110">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="839d6-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="839d6-111">См. также</span><span class="sxs-lookup"><span data-stu-id="839d6-111">See also</span></span>

- [<span data-ttu-id="839d6-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="839d6-112">Authenticode</span></span>](index.md)
